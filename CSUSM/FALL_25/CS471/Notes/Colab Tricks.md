---
tags:
  - ai
  - CS471
  - CSUSM
  - colab
  - medium
---

# Google Colab Tips & Tricks (2021)

A concise collection of handy tips and tricks for enhancing your Colab experience, based on Nandan Manjunatha’s “Google Colab Tips and Tricks — 2021” [Medium+8Medium+8Medium+8](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com).

---

## 1. Prevent Idle Timeout Disconnect

To keep Colab from disconnecting during long runs, paste the following JavaScript into the browser console:

`function ClickConnect(){     console.log("Clicked on star button");      document.querySelector("iron-icon#star-icon").click();   } setInterval(ClickConnect, 1200000); // every 2 minutes`

- Opens the console:
    
    - Windows: `F12`
        
    - Firefox (Linux): `Ctrl + Shift + K`
        
    - Chrome (Linux): `Ctrl + Shift + J`
        
- It simulates clicking the star icon beside the filename so your session stays active. [Medium+1](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)
    

---

## 2. Useful Code Snippets

A handful of commonly used snippets to streamline workflows:

- **Mount Google Drive**
    
    `from google.colab import drive   drive.mount('/content/drive/')   %cd '/content/drive/My Drive/your_project_path'`
    
- **Upload Files**
    
    `from google.colab import files   files.upload()`
    
- **Download Files**
    
    `from google.colab import files   files.download('path/to/file')`
    
- **Open TensorBoard**
    
    `%load_ext tensorboard   %tensorboard --logdir checkpoints/train`
    
- **GPU Info via TensorFlow**
    
    `import tensorflow as tf   print(tf.__version__)   print(tf.config.list_physical_devices('GPU'))`
    
- **GPU Usage (Nvidia)**
    
    `!nvidia-smi`
    
- **CPU Details**
    
    `!cat /proc/cpuinfo`
    

[Medium+3Medium+3Medium+3](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)[Medium](https://manavmandal.medium.com/image-classifier-using-cnns-4cc040a5ea4c?source=rss-------1&utm_source=chatgpt.com)

---

## 3. Use Bash Within a Cell

Execute multiple bash commands in a single cell without prefixing with `!`:

`%%bash # your bash commands here`

[Medium+1](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)

---

## 4. Handy Keyboard Shortcuts

- **Run selected part of a cell**: `Ctrl + Shift + Enter`
    
- **Run a cell**: `Ctrl + Enter`
    
- **Run cell + insert new below**: `Alt + Enter`
    
- **Run cell + go to next**: `Shift + Enter`
    
- **Toggle comment on line**: `Ctrl + /`
    
- **Indent/Dedent**: `Ctrl + ]` / `Ctrl + [` [Medium+8Medium+8Medium+8](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)
    

---

## 5. Open GitHub Notebook Directly in Colab

To open any `.ipynb` from GitHub in Colab:

1. Locate the GitHub notebook URL, e.g.,:
    
    `https://github.com/user/repo/blob/main/notebook.ipynb`
    
2. Replace `github.com` with `githubtocolab.com`:
    
    `https://githubtocolab.com/user/repo/blob/main/notebook.ipynb`
    

Then hit Enter; the notebook opens directly in Colab. [Medium+7Medium+7Medium+7](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)

---

## 6. Interactive Data Table in Notebook

To explore tabular data with sorting, filtering, and interactive features:

`%load_ext google.colab.data_table  import pandas as pd df = pd.read_csv("your_data.csv") df`

This enables an interactive table interface within the notebook. [Medium+1](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)

---

## 7. View Cell Output in Fullscreen

To focus on lengthy training logs or visual outputs:

1. Click the “More actions” (three-dot) button on the right side of the cell.
    
2. Select **“View output fullscreen”** to expand the output area.
    

Such fullscreen visualization is ideal for monitoring ongoing training or inspecting long outputs.[Medium+4Medium+4Medium+4](https://medium.com/curious-manava/google-colab-tips-and-tricks-2021-58e6289cc0fc?utm_source=chatgpt.com)

---

### TL;DR Table

|Tip|Description|
|---|---|
|Prevent Idle Disconnect|Inject JS into console to auto-click star icon every 2 min|
|Code Snippets|Drive mount, uploads, downloads, TensorBoard, hardware info|
|Bash in Cell|Use `%%bash` magic for multiple shell commands|
|Shortcuts|Quick-run cells, comment, indent, navigate|
|GitHub Integration|Open `.ipynb` from GitHub by replacing domain|
|Interactive Table|Use `%load_ext google.colab.data_table` to explore data|
|Fullscreen Output|Expand cell output for better visibility|