# 🎨 Generative AI Workshop: Running ComfyUI on Google Colab (T4 GPU)

Welcome to the hands-on ComfyUI workshop! In this guide, you will learn how to launch **ComfyUI** on a free cloud **NVIDIA T4 GPU (16GB VRAM)** using Google Colab, and how to import our pre-built **Text-to-Image (`t2i.json`)** workflow directly from this GitHub repository.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<YOUR_GITHUB_USERNAME>/<YOUR_REPO_NAME>/blob/main/run_compyui.ipynb)

---

## 📋 Repository Files

| File Name | Description |
| :--- | :--- |
| 📓 **`run_comfyui.ipynb`** | The Google Colab notebook that installs ComfyUI, downloads the AI models, and creates a public web link. |
| 📄 **`t2i.json`** | The **Text-to-Image (T2I)** ComfyUI workflow file you will import into the ComfyUI canvas. |

---

## 🚀 Step 1: Open the Notebook in Google Colab

You can open `run_comfyui.ipynb` in Google Colab using **either** of the two methods below:

### Method A: One-Click Badge (Fastest)
1. Click the blue **Open in Colab** badge at the top of this page.
2. Make sure you are signed in with your **Google Account**.

### Method B: Open Directly from Google Colab
1. Go to [https://colab.research.google.com/](https://colab.research.google.com/).
2. In the pop-up window (or via **File ➔ Open notebook**), click the **GitHub** tab on the left.
3. Paste the URL of this GitHub repository into the search bar and press **Enter**.
4. Click on **`run_comfyui.ipynb`** to open it.

---

## ⚡ Step 2: Set the Runtime Machine to Use the T4 GPU

By default, Google Colab may start on a slow CPU machine. **You must switch your runtime machine to a T4 GPU before running any code!**

1. In the top menu bar of Google Colab, click **Runtime ➔ Change runtime type** *(or click the small dropdown arrow `▾` next to **Connect** in the top-right corner and select **Change runtime type**)*.
2. Under **Runtime type**, keep **`Python 3`**.
3. Under **Hardware accelerator**, select **`T4 GPU`**.
4. Click **Save**.
5. In the top-right corner, click **Connect**. Wait a few seconds until you see a green checkmark `✔` next to **T4** (showing `RAM` and `Disk` bars).

```text
Top Menu: Runtime ➔ Change runtime type ➔ Hardware accelerator: [ T4 GPU ] ➔ Save
```

> **💡 Optional Verification:** If you want to double-check that your T4 GPU (16GB VRAM) is active, you can run `!nvidia-smi` in a code cell.

---

## ▶️ Step 3: Run `run_comfyui.ipynb` and Open ComfyUI

1. Scroll through **`run_comfyui.ipynb`** and click the **Play button (`▶`)** on the left side of each code cell from top to bottom *(or click **Runtime ➔ Run all** in the top menu)*.
2. If Google Colab shows a warning saying *"This notebook was not authored by Google"*, click **Run anyway**.
3. **Wait for Setup & Model Downloads (approx. 3–5 minutes):**
   * The notebook will install ComfyUI, download the required checkpoints/models, and start the ComfyUI server.
4. **Click the Public Web URL:**
   * At the bottom of the last running cell's output log, look for a public tunnel link (usually ending in **`.trycloudflare.com`**, **`.gradio.live`**, or **`ngrok-free.app`**):
   ```text
   To see the GUI go to: https://xxxx-xxxx-xxxx.trycloudflare.com
   ```
   * Click that link to open the **ComfyUI visual workspace** in a new browser tab!
   * ⚠️ **Important:** Keep your Google Colab tab open and running in the background while using ComfyUI.

---

## 📥 Step 4: Download & Import `t2i.json` from GitHub into ComfyUI

Now that your ComfyUI canvas is open in your browser, let's load the **`t2i.json`** workflow from this repository:

### 4.1 Download `t2i.json` from GitHub to Your Computer
1. Come back to this GitHub repository tab and click on the file **`t2i.json`** in the file list above.
2. In the top-right corner of the file preview box, click the **Download raw file** button (`⬇` icon) to save `t2i.json` to your computer's `Downloads` folder.
   *(Tip: Do NOT right-click the file name on the main repo page and "Save Link As", as that saves an HTML webpage instead of the JSON file!)*

### 4.2 Import `t2i.json` into ComfyUI
Switch back to your **ComfyUI browser tab** and use **either** of these two methods:

* **Method 1 (Drag & Drop — Easiest):** Open your computer's `Downloads` folder, click and drag **`t2i.json`**, and drop it directly onto the dark ComfyUI canvas!
* **Method 2 (Menu Load):** Click the **Workflow** menu in the top-left corner of ComfyUI ➔ select **Open** (or press **`Ctrl + O`** / **`Cmd + O`**) ➔ select **`t2i.json`** from your `Downloads` folder.

---

## 🖼️ Step 5: Generate Your First Image!

1. Once `t2i.json` loads onto the canvas, locate the **CLIP Text Encode (Positive Prompt)** node and type what you want to generate.
2. Click the blue **Queue** button (or press **`Ctrl + Enter`**).
3. Watch the green highlight border move from node to node (`Load Checkpoint` ➔ `CLIP Text Encode` ➔ `KSampler` ➔ `VAE Decode` ➔ `Save Image`).
4. Right-click on the generated image inside the **Save Image** node and select **Save Image** to download it to your computer! *(Remember: Google Colab deletes temporary cloud files when your session ends, so always download your favorite results!)*

---

## 🛠️ Troubleshooting & FAQ

* **❓ Error: *"SyntaxError"* or *"Invalid JSON"* when importing `t2i.json`?**
  * You likely saved the GitHub HTML webpage instead of the raw JSON file. Click on `t2i.json` in GitHub first, then click the **Download raw file (`⬇`)** button at the top-right of the code box.
* **❓ Error: *"Cannot connect to GPU backend"* in Google Colab?**
  * Free Google Colab accounts have daily GPU usage limits. Make sure you disconnect other open Colab notebooks (**Runtime ➔ Manage sessions ➔ Terminate**), or switch to a backup Google account.
* **❓ The `.trycloudflare.com` link shows a Bad Gateway (502) error?**
  * You clicked the link a few seconds too early while ComfyUI was still booting up. Wait 15–20 secondsuntil the Colab output says `To see the GUI go to: http://127.0.0.1:8188`, then refresh the `.trycloudflare.com` tab.
* **❓ What happens when I finish the workshop?**
  * First, download any images you want to keep. Then, in Google Colab, click **Runtime ➔ Disconnect and delete runtime** so you don't use up your free GPU quota!
