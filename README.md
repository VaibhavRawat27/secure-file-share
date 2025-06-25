# 🔐 Secured File Share

**Secured File Share** is a lightweight, privacy-first file sharing platform built with **Streamlit** and **Cloudinary**. It allows users to securely upload any file format and generate private links and QR codes for sharing. Files are **automatically deleted after a user-defined time** and are **protected with passwords** — no login or signup required.

🌐 **Live Demo:** [secured-file-share.streamlit.app](https://secured-file-share.streamlit.app/)

---

## 🚀 Features

- 📁 Upload & share any file instantly (PDF, ZIP, EXE, MP4, etc.)
- 🔐 Password-protected access for every upload
- ⏱️ Auto-delete after selected expiry time (1–48 hours)
- 🔗 Secure link + 📱 QR code generation
- ⚡ Simple UI, mobile-friendly, and fully responsive
- 🧾 Public file ID and expiry timer display
- ✅ No login/account required
- 🌐 Entirely hosted on **Streamlit Cloud** with **Cloudinary backend**

---

## 🧰 Tech Stack

| Layer      | Technology                 |
|------------|----------------------------|
| Frontend   | [Streamlit](https://streamlit.io/) |
| File Storage | [Cloudinary](https://cloudinary.com/) (raw upload API) |
| QR Code    | `qrcode` Python package    |
| File Handling | `BytesIO`, `requests`, `time` |
| UI/UX      | Custom HTML + Tailwind-inspired design |
| Language   | Python 3.10+               |

---

## 📦 How It Works

1. 🎯 **Upload** any file using the interface.
2. 🔑 Set a password and expiry time (1 to 48 hours).
3. ☁️ File is uploaded to **Cloudinary** under your configured folder.
4. 🔗 A **secure link** is generated: `...?file=<unique_id>`
5. 🔒 The receiver must enter the correct password to **access/download**.
6. ⌛ The system automatically **denies access** after expiry.
7. 📱 A **QR Code** is generated for instant mobile scanning.

---

## 🖥️ Local Setup Instructions

Follow the steps below to run the project locally on your machine:

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/vaibhavrawat27/SecureShare.git
cd SecureShare
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install streamlit cloudinary qrcode requests
```

### 3️⃣ Set Up `.streamlit/secrets.toml`

Create a file: `.streamlit/secrets.toml` and add your **Cloudinary credentials**:

```toml
[cloudinary]
cloud_name = "your_cloud_name"
api_key = "your_api_key"
api_secret = "your_api_secret"
UPLOAD_FOLDER = "secured-share"

# Optional admin password if used for access
CORRECT_PASSWORD = "admin123"
```

> 🔐 Get credentials by signing up at [https://cloudinary.com](https://cloudinary.com)

### 4️⃣ Run Locally

```bash
streamlit run app.py
```

App will open at: [http://localhost:8501](http://localhost:8501)

---

## 🧪 Test Mode / Notes

- App is in test mode — **monitor your Cloudinary usage** for bandwidth and storage.
- Files are uploaded as `resource_type="raw"` to allow **any file format**.
- Expiry is handled using timestamps stored in metadata (`context`) and checked during access.

---

## 🛡️ Security & Privacy

- No file or password is stored in any local database.
- All files are **automatically deleted** by denying access after expiry (timestamp).
- File download is protected by **password field** entered during upload.
- Shared links contain only the public Cloudinary ID and no sensitive data.

---

## 📚 Example Use Cases

- 🔐 Share confidential documents with clients
- 🎓 Share project files with time-bound access
- 📤 Temporary uploads for presentations or demos
- 📱 Easily scan QR and access from mobile

---

## 💡 Future Improvements (Open to PRs)

- ✅ Email notification on upload/access
- 🔄 One-time download (self-destruct)
- ⏳ Live countdown UI
- 🧾 File preview (PDF, image)
- 📦 Batch upload & zip download
- 📊 Usage tracking per file ID

---

## 🤝 Contribution

Contributions are welcome!  
Feel free to fork this project, improve it, and submit a pull request.

```bash
# Fork, Clone, Commit, Push, PR ✅
```

---

## 🧑‍💻 Author

Made with ❤️ by **Vaibhav Rawat**

📧 Email: [rawatvaibhav27@gmail.com](mailto:rawatvaibhav27@gmail.com)  
🌐 Portfolio: [vaibhavrawat.in](https://vaibhavrawat.in)  
🐙 GitHub: [@vaibhavrawat27](https://github.com/vaibhavrawat27)

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, fork, and remix.

---

## 🔗 GitHub Repo

👉 [github.com/vaibhavrawat27/SecureShare](https://github.com/vaibhavrawat27/Secured-file-Share)
