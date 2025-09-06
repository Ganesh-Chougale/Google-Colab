### **In Colab: Local machine vs Drive**

| Feature                   | Local Machine                | Google Drive                               |
| ------------------------- | ---------------------------- | ------------------------------------------ |
| Upload single file        | ✅ `files.upload()`           | ✅ Not needed                               |
| Upload folder             | ✅ (zip + unzip trick)        | ✅ Mount whole Drive                        |
| Persistent access         | ❌ Only temporary for session | ✅ Files stay forever                       |
| Automatic mounting        | ❌ Not possible               | ✅ `drive.mount()` gives full folder access |
| Read/write during runtime | ✅ While uploaded             | ✅ Full access anytime                      |
| Easy collaboration        | ❌ No                         | ✅ Yes, shared Drive                        |

---

* **Single file or folder upload from local**: works, but **temporary**.
* **Mounting a local directory**: **not possible** because Colab runs on a cloud VM; your local filesystem is separate.
* **Persistent workflow**: use **Google Drive** for files and folders.

---

*can* combine both:

1. Upload temporary files from your local machine for quick testing.
2. Move them into your **Drive Input folder** to make them persistent.