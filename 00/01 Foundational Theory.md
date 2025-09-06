### 🏗️ Foundations of Google Colab

1. **Cloud Jupyter Notebook**

   * It’s like Jupyter Notebook but hosted on Google’s servers.
   * Runs Python code (mainly for data science, ML, research).

2. **Backed by Virtual Machines**

   * Every Colab session runs on a temporary **VM (Linux environment)** in Google Cloud.
   * You can pick **CPU / GPU / TPU** accelerators.

3. **Temporary Workspace**

   * You get a sandbox with limited RAM & disk.
   * Anything saved locally (`/content/`) **disappears after session ends**.
   * To persist, mount **Google Drive** or push to GitHub.

4. **Preloaded with Libraries**

   * ML/DL packages (TensorFlow, PyTorch, OpenCV, NumPy, Pandas, etc.) already installed.
   * Saves you setup hassle.

5. **Interactive + Shareable**

   * Notebook has code + text (Markdown, LaTeX, images).
   * Shareable like Google Docs (others can view/run your code).

6. **Free + Paid Tiers**

   * **Free:** GPU/TPU, but limited hours, disconnects after inactivity, sometimes no GPU available.
   * **Pro/Pro+:** Priority GPUs, longer runtimes, more RAM.

👉 So in short: **Colab = Google’s free online Python lab with GPUs, built on Jupyter**.