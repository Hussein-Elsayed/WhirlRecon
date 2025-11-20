# 🌪️ WhirlRecon

> A powerful, automated, multi-target reconnaissance framework for Bug Bounty hunters.
> **Written by:** Wh1rlw1nd

![Bash](https://img.shields.io/badge/Language-Bash-4EAA25?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Security](https://img.shields.io/badge/Category-Recon-red?style=for-the-badge)

## 📖 Overview

**WhirlRecon** is a wrapper script that automates the entire reconnaissance process for multiple targets. It chains together the best industry-standard tools to perform subdomain enumeration, port scanning, web probing, URL gathering, JavaScript analysis, and vulnerability scanning.

It organizes the output into a clean directory structure for every domain found in your target list.

---

## 🛠️ Features

- **Multi-Target Support:** Feeds from a `targets.txt` file to scan hundreds of domains in one go.
- **Scope Management:** Automatically excludes out-of-scope domains using a blacklist file.
- **Smart Filtering:** Uses `anew` to prevent duplicate entries.
- **Organized Output:** Creates a dedicated folder for each domain with categorized results.
- **Vulnerability Scanning:** Integrates `Nuclei` for automated bug detection.

| Tool | Purpose |
| :--- | :--- |
| **Subfinder** | Fast passive subdomain enumeration |
| **Assetfinder** | Finding domains and subdomains |
| **Findomain** | Fast subdomain enumeration |
| **Naabu** | Fast port scanning |
| **Httpx** | HTTP probing and web server fingerprinting |
| **Gauplus** | Fetching known URLs from AlienVault/Wayback |
| **Hakrawler** | Active web crawler |
| **Subjs** | Extracting JavaScript file links |
| **Nuclei** | Template-based vulnerability scanner |
| **Anew** | Appending new lines to files (filtering) |

---

## 🚀 Installation

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/WhirlRecon.git](https://github.com/YOUR_USERNAME/WhirlRecon.git)
   cd WhirlRecon
2. Make the script executable:
   ```bash
   chmod +x whirlrecon.sh
3. (Optional) Install Dependencies: If you have Go installed, you can run the following commands to install all necessary tools:
   ```bash
   go install -v [github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest](https://github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest)
   go install -v [github.com/projectdiscovery/naabu/v2/cmd/naabu@latest](https://github.com/projectdiscovery/naabu/v2/cmd/naabu@latest)
   go install -v [github.com/projectdiscovery/httpx/cmd/httpx@latest](https://github.com/projectdiscovery/httpx/cmd/httpx@latest)
   go install -v [github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest](https://github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest)
   go install -v [github.com/tomnomnom/anew@latest](https://github.com/tomnomnom/anew@latest)
   go install -v [github.com/tomnomnom/assetfinder@latest](https://github.com/tomnomnom/assetfinder@latest)
   go install -v [github.com/lc/gau/v2/cmd/gau@latest](https://github.com/lc/gau/v2/cmd/gau@latest)
   go install -v [github.com/hakluke/hakrawler@latest](https://github.com/hakluke/hakrawler@latest)
   go install -v [github.com/lc/subjs@latest](https://github.com/lc/subjs@latest)
💻 Usage
1. Add your targets
Create a file named targets.txt and add your domains (one per line).

2. (Optional) Define Out-of-Scope
Create a file named out_of_scope.txt to prevent scanning specific subdomains.

3. Run the script
Run the script, passing the target file as an argument:
   ```bash
   ./whirlrecon.sh targets.txt

### 📂 Output Structure

The script creates a `results/` directory in the root of the repository, and inside that, a dedicated folder for every domain scanned:

```text
results/
├── [target.com/](https://target.com/)
│   ├── subdomains.txt       # Final list of in-scope subdomains
│   ├── live_hosts.txt       # Live web servers (HTTP/HTTPS) found by httpx
│   ├── all_urls.txt         # Crawled and historical URLs
│   ├── js_files.txt         # Extracted JavaScript file links
│   └── nuclei_results.txt   # Vulnerabilities found by Nuclei
└── [another-target.com/](https://another-target.com/)
    └── ...
```

⚠️ Disclaimer
This tool is for educational purposes and authorized security testing only. Do not use this tool on targets you do not have explicit permission to test. The author is not responsible for any misuse.

### 3. GitHub Repository Name

When creating your repository on GitHub, you should name it: **`WhirlRecon`** (or `whirlrecon` if you prefer all lowercase).

Now you are ready to commit and push your finalized tool!
