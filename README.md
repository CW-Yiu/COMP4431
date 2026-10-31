# 🎨 Generative AI Workshop: Running ComfyUI on Kaggle Notebooks (T4 GPU)

Welcome to the hands-on ComfyUI workshop! In this guide, you will learn how to launch **ComfyUI** on a free cloud **NVIDIA T4 GPU (`GPU T4 x2`)** using **Kaggle Notebooks**, and how to import our pre-built **Text-to-Image (`t2i.json`)** workflow directly from this GitHub repository.

[![Open in Kaggle](https://kaggle.com/static/images/open-in-kaggle.svg)](https://kaggle.com/kernels/welcome?src=https://github.com/CW-Yiu/COMP4431/blob/main/run_comfyui.ipynb)

---

## 📋 Repository Files

| File Name | Description |
| :--- | :--- |
| 📓 **`run_comfyui.ipynb`** | The Kaggle notebook that installs ComfyUI, downloads the AI models, and creates a public web link. |
| 📄 **`t2i.json`** | The **Text-to-Image (T2I)** ComfyUI workflow file you will import into the ComfyUI canvas. |

---

## 🚀 Step 1: Open the Notebook in Kaggle

You can open `run_comfyui.ipynb` in Kaggle using **either** of the two methods below:

### Method A: One-Click Badge (Fastest)
1. Click the blue **Open in Kaggle** badge at the top of this page.
2. Sign in to your **Kaggle Account** (you can sign in directly with your Google Account).
3. *(If prompted, click **Copy & Edit** in the top-right corner to open your own editable session).*

### Method B: Import Directly from Kaggle
1. Go to [https://www.kaggle.com/](https://www.kaggle.com/) and sign in.
2. In the left navigation sidebar, click **+ Create ➔ New Notebook**.
3. In the top menu bar of the notebook editor, click **File ➔ Import Notebook**.
4. Select the **GitHub** tab (or upload `run_comfyui.ipynb` from your computer), paste the URL of this notebook (`https://github.com/CW-Yiu/COMP4431/blob/main/run_comfyui.ipynb`), and click **Import**.

---

## ⚡ Step 2: Enable the T4 GPU & Turn On Internet Access

By default, Kaggle starts on a slow CPU with internet disabled. **You must enable both the T4 GPU and Internet Access before running any code!**

> ⚠️ **First-Time Kaggle Users (Phone Verification):** Kaggle requires your account to be **Phone Verified** via SMS before allowing free GPU and Internet access. If the GPU or Internet options are greyed out, go to [Kaggle Settings](https://www.kaggle.com/settings) ➔ **Phone Verification** and verify your phone number first.

1. Open the **Notebook Options** panel on the right-hand sidebar of Kaggle *(if the right sidebar is hidden, click the **`|◁`** panel icon in the top-right/bottom-right corner, or use the top menu **Settings**)*.
2. Under **Accelerator**, change `None` to **`GPU T4 x2`** *(or click **Settings ➔ Accelerator ➔ GPU T4 x2** in the top menu)*.
3. When prompted with *"Turn on GPU?"*, click **Turn on GPU**.
4. In the same right-hand **Notebook Options** panel, scroll down to **Internet** and toggle the switch **ON** (`Internet on`).
   *(Crucial: Without Internet turned on, Kaggle cannot download ComfyUI, AI models, or create the public web URL!)*

```text
Right Sidebar (Notebook Options): Accelerator: [ GPU T4 x2 ]  +  Internet: [ ON ]
