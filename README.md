# Mars

A **SIMPLE YOLOv8 detection model** implementation, supporting:

- ✅ Basic detection model training and evaluation
- 🎓 Teacher-student **knowledge distillation**
- 🔁 Swappable backbones like **Swin Transformer**

## Entry Point

```bash
cd <path_to_project_root> && python mars.py
````

## Configuration

Before running the project, you **must specify or create a configuration file** in:

```
<path_to_project_root>/cfgops/
```

The config file defines paths, model settings, training hyperparameters, and **tags**.

See `cfgops/c1.py` for an example.

## Config Tags (`cfgname`)

Each config file contains a `tags` list，used to **enable or disable optional components**：

| Tag               | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| `full`            | Enables basic training and detection functionality (default) |
| `teacher`         | Loads a pretrained **teacher model**                         |
| `distillation`    | Enables **knowledge distillation** from teacher to student   |
| `swintransformer` | Uses **Swin Transformer** as backbone instead of default     |

Modify it in `mars.py`, here are some examples:

```python
cfgname="c1.nano.full",
# cfgname="c1.nano.full.cuda@3",
# cfgname="c1.nano.teacher",
# cfgname="c1.nano.distillation",
# cfgname="c1.nano.swintransformer",
```

## Dependencies

Install required packages via:

```bash
pip install -r requirements.txt
```

Package `timm` is for Swin Transformer.
