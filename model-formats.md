# AI Model Formates

Storing AI models involves various file formats, each serving specific purposes such as model architecture, weights, or interoperability between different frameworks. Here is a list of commonly used file formats for storing AI models:

### General Formats

1. **HDF5 (.h5 or .hdf5)**
   - Used by Keras to store model architecture, weights, and training configuration.
   - Example: `model.h5`

2. **ONNX (.onnx)**
   - Open Neural Network Exchange format used for interoperability between different deep learning frameworks.
   - Example: `model.onnx`

3. **Pickle (.pkl)**
   - General Python object serialization format used to save model objects.
   - Example: `model.pkl`

### TensorFlow-Specific Formats

4. **TensorFlow SavedModel**
   - Directory format containing a saved model, including its architecture, weights, and other information.
   - Example: `saved_model.pb`

5. **TensorFlow Checkpoint (.ckpt)**
   - Stores TensorFlow model weights.
   - Example: `model.ckpt`

### PyTorch-Specific Formats

6. **PyTorch Script Module (.pt or .pth)**
   - Used by PyTorch to store models in a way that includes both architecture and weights.
   - Example: `model.pt`

7. **PyTorch State Dictionary (.pth or .pt)**
   - Stores only the model weights.
   - Example: `model_state.pth`

### MXNet-Specific Formats

8. **MXNet Model (.params)**
   - Stores MXNet model parameters.
   - Example: `model.params`

9. **MXNet JSON (.json)**
   - Stores the MXNet model architecture.
   - Example: `model-symbol.json`

### Caffe-Specific Formats

10. **Caffe Model (.caffemodel)**
    - Stores Caffe model weights.
    - Example: `model.caffemodel`

11. **Caffe Prototxt (.prototxt)**
    - Stores the Caffe model architecture.
    - Example: `deploy.prototxt`

### Other Formats

12. **TorchScript (.pt or .pth)**
    - A format used by PyTorch for serialized code and data that can be run independently from the code that created it.
    - Example: `traced_model.pt`

13. **Core ML (.mlmodel)**
    - Used by Apple's Core ML framework for deploying models on iOS devices.
    - Example: `model.mlmodel`

14. **FlatBuffers**
    - Used by TensorFlow Lite for storing models in a lightweight, cross-platform format.
    - Example: `model.tflite`

15. **Protocol Buffers (Protobuf) (.pb)**
    - Commonly used by TensorFlow for serialized data, including model graphs.
    - Example: `model.pb`

16. **Safetensor (.safetensor)**
    - A secure format for storing tensor data to avoid arbitrary code execution vulnerabilities.
    - Example: `model.safetensor`

17. **GGUF (.gguf)**
    - A format for representing computational graphs, providing a standardized way to describe and share them.
    - Example: `model.gguf`

18. **PaddlePaddle (.pdparams, .pdmodel)**
    - Used by PaddlePaddle to store model parameters and architecture.
    - Example: `model.pdparams`, `model.pdmodel`

Choosing the right format depends on the framework you are using and the specific requirements of your project, such as model portability, deployment platform, and security considerations.
