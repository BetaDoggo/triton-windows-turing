# triton-windows 3.7.1 for turing (20 series cards) (yes it's real) (for comfyui-int8-fast)

**triton-windows 3.7.1** compiled with fullish turing support. It should make MMAv2 work, which is good, or so my consultant says.

## But why?

Some triton features have been disabled on turing since the release of 3.3, which seems to break the comfyui-int8-fast nodes. I wasted more time that I would have liked to get this working so I'm uploading my prebuilt wheel and some instructions to make myself feel better.

## Requirements

- Windows (obviously)
- **Python 3.11** (I'm not going to compile for other versions because I'm lazy)
- Microsoft Visual C++ Redistributable 2015-2022, x64, **version 14.44 or newer**
  ([`vc_redist.x64.exe`](https://aka.ms/vs/17/release/vc_redist.x64.exe))
- PyTorch compatible with triton 3.7 (torch 2.11 / 2.12)

## Install

First remove any existing triton, then install this wheel:
```
python.exe -m pip uninstall -y triton triton-windows
python.exe -m pip install https://github.com/BetaDoggo/triton-windows-turing/releases/download/wheel/triton_windows-3.7.1-cp311-cp311-win_amd64.whl
```

### **IMPORTANT**, for portable install:

If you use the portable comfy install you also need the
CPython development headers and `python311.lib` in that folder. 

Here's how to get them:

1. Download `python_3.11.9_include_libs.zip` from
   https://github.com/woct0rdho/triton-windows/releases/download/v3.0.0-windows.post1/python_3.11.9_include_libs.zip
2. Merge `include\*` into `python_embeded\Include`
3. Create `python_embeded\libs\` and copy `python311.lib` and `python3.lib` into it.
4. Pray

