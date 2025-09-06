```python
import torch

if torch.cuda.is_available():
    print("✅ GPU available:", torch.cuda.get_device_name(0))
else:
    print("❌ No GPU");
```  
#### Output: if GPU not available  
```console
❌ No GPU
```  
#### Output: if GPU available    
```console
✅ GPU available: Tesla T4
```  