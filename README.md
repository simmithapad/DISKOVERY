## 🧪 DISKOVERY: Disk Forensics Tool for Data Categorization & Keyword Filtering

**DISKOVERY** is a Python-based digital forensics tool designed to analyze disk images. It performs a multi-stage forensic analysis including imaging, partition parsing, file categorization, keyword-based filtering, and automatic PDF reporting. The tool supports both complete and filtered analysis outputs and provides investigators with a concise overview of disk contents.  It is a command-line interface (CLI) tool that works well on **Ubuntu** and **Debian-based systems**.

---

### ⚙️ Features
- **Disk Image Support** (`.img`, `.E01`, `.dd`)
- **Partition Parsing** using `mmls`
- **File Categorization**:
  - Deleted
  - Encrypted
  - Current
  - Hidden
- **File Type Filtering** (e.g., `.pdf`, `.docx`)
- **Keyword Search** in extracted text-based files
- **Visual Summary** via pie charts
- **PDF Report Generation** with listings, and visualizations

---

### 📁 Project Structure
```
diskovery/
├── diskovery/                       # Main package
│   ├── __init__.py
│   ├── main.py                      # CLI entry point
│   ├── stages/                      # Stage-wise modular pipeline
│   │   ├── __init__.py
│   │   ├── stage1_disk_imaging.py
│   │   ├── stage2_extraction.py
│   │   ├── stage3_categorization.py
│   │   ├── stage4_filtering.py
│   │   ├── stage4_2_keyword.py
│   │   └── stage5_reporting.py
│   └── utils/                       # Utility functions
│       ├── __init__.py
│       └── run_command.py
│
├── README.md                        # Project overview and usage
├── LICENSE                          # MIT License
├── setup.py                         # Packaging configuration
├── requirements.txt                 # Python dependencies
├── MANIFEST.in                      # Include non-code files for PyPI
├── pyproject.toml                   # Build configuration
└── .gitignore                       # Git ignore rules
```

---

### 🚀 Quick Start

#### ✅ Option 1: Install from PyPI (Recommended)
```bash
pip install diskovery
```

Then run the tool globally from anywhere:
```bash
diskovery
```

#### ✅ Option 2: Clone the Repository (for development)

#### 1. Clone the Repository
```bash
git clone https://github.com/simmithapad/DISKOVERY.git
cd DISKOVERY
```

#### 2. Set Up Environment  (Installs Tools + Python Packages)
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
sudo apt update && sudo apt install -y dcfldd sleuthkit binwalk grep pdfgrep
```

#### 3. Run the Tool
```bash
python3 diskovery/main.py
```
### Example Usage 
1. Insert your USB device.
2. Check where it's mounted:
```bash
sudo fdisk -l
```
<img src="https://github.com/user-attachments/assets/77b0b981-3d36-4c47-9e19-4cef14787032" width="500px" />

3. Run DISKOVERY (choose one):
- If installed via pip:
```bash
sudo diskovery
```
- If running from source:
```bash
sudo python3 diskovery/main.py
```
<img src="https://github.com/user-attachments/assets/6533f9cd-5b1c-4da1-87f7-277f1b9e155f" width="900px" />

---

### 🛠️ Dependencies
#### System Tools
- `dcfldd`
- `sleuthkit` (for `mmls`, `fls`, `fsstat`)
- `binwalk`
- `grep` and `pdfgrep`

#### Python Packages
- `fpdf`
- `docx2txt`
- `re`

---

### 📄 Output
- Disk images saved in `./output_files/`
- PDF reports saved in `./output_files/reports/`
- Extracted files saved in `./output_files/extracted_files/`

---

### 📬 Future Work
- [ ] GPU Acceleration
- [ ] Memory Forensics Integration

---

### 👤 Author
Simmi Thapad   
Vrinda Abrol  
Vrinda Diwakar  
Ankita Ghosh

---

### License
 This project is licensed under the MIT License - see the LICENSE file for details.

 ---

### 🔒 Disclaimer
> [!Important]
> This tool is intended for **educational and lawful forensic analysis** only. Use responsibly.
