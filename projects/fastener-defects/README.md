# Fastener Defect Inspection (live demo)

Upload a photo of a nut, washer or screw and a MobileNetV2 classifier running **in the browser** (TensorFlow.js) answers **OK** or **NOK**.
No backend, no upload: the image stays on the device. Works on GitHub Pages.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole demo (HTML + CSS + JS). TensorFlow.js 4.22.0 is loaded from jsDelivr on first use. |
| `model/model.json`, `model/*.bin` | The trained model converted to the TF.js graph format (float32, 8.7 MB). |
| `model/class_names.json` | Class order, which classes are OK, input size. The page reads this file. |
| `samples/` | 18 random images from the held-out **test** split. |

## How the model was made

* Code: `M1DSAI/DL/train_fastener.py` in <https://github.com/haJye/DSAI>.
* MobileNetV2 (ImageNet) + Dropout + 6-way softmax, 224×224 input. Preprocessing (`x/127.5 - 1`) is **inside** the model, so the page feeds raw 0–255 pixels.
* Stage 1 trains the new head with the base frozen, stage 2 fine-tunes the last 40 layers at lr 1e-5 (BatchNorm frozen).
* Split per class: 70 % train / 15 % validation / 15 % test, exact duplicate files removed first.
* Test set (439 images): 98.6 % 6-class accuracy, 98.9 % OK/NOK accuracy, 217 of 222 NOK parts caught, 217 of 217 OK parts passed.
* The split is random per file. Near-identical photos of the same part may exist on both sides, so the figures are likely optimistic for truly new parts.

## Replacing the model

```bash
# train_fastener.py writes outputs/saved_model
pip install tensorflowjs
tensorflowjs_converter --input_format=tf_saved_model --output_format=tfjs_graph_model \
  --signature_name=serving_default --saved_model_tags=serve outputs/saved_model model/
cp outputs/class_names.json model/
```

Do **not** use `--quantize_uint8`: it changed the predictions of 2 of 18 test images. float16 quantisation (`--quantize_float16 '*'`, 4.4 MB) stayed within 0.7 % of float32 and is an option if size matters.

## Checks done

* Browser (TF.js, float32) versus the Python SavedModel on 18 images: max probability difference 3e-6 when both decode the image with the same JPEG decoder.
* Versus the probabilities printed by the Colab run: below 2 %. The only reason is that TensorFlow and browsers use different JPEG decoders.

## Limits

Trained on nuts, washers and screws photographed in one setup. Any other image still gets an OK/NOK answer. This is a portfolio demo, not a quality-control tool.
