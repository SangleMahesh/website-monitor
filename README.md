# 🚀 Website Monitoring Tool

A terminal-based website monitoring tool using **Python, aiohttp, and Textual** to check website uptime, response times, and status codes.

---

## 📌 Features
✅ Asynchronous website availability checking  
✅ Displays **HTTP status codes, response times, and timestamps**  
✅ **Color-coded** status indicators for quick insights  
✅ Periodic automatic checks (default: **30s**)  
✅ Simple CLI interface with easy setup  

---

## 🛠️ Installation  

### **1️⃣ Clone the Repository**  
```sh
git clone https://github.com/your-username/website-monitor.git
cd website-monitor
```

### **2️⃣ Install Dependancies**
```sh
pip install -r requirements.txt
```

### **2️⃣ Create a File with URLs to Monitor**
```sh
echo "https://google.com" > urls.txt
echo "https://github.com" >> urls.txt
```
## 🎯 Usage
```sh
python script.py urls.txt -i 60
```
urls.txt → File containing websites to monitor (one per line)
-i 60 → Interval for checks (default: 30 seconds)


## 📊 Example Output
-------------------------------------------------
| URL                | Status | Response Time | Last Checked |
-------------------------------------------------
| https://google.com | 200    | 0.23s        | 2025-03-22 14:30:10 |
| https://github.com | 503    |  N/A         | 2025-03-22 14:30:10 |
-------------------------------------------------

Color Codes:
🟢 Green → Website is up (200-399)
🟡 Yellow → Client error (400-499)
🔴 Red → Server error (500+ or timeout)

## 🔧 Configuration
### Modify Check Interval
The script checks URLs every 30 seconds by default. Change this with -i <seconds>:
```sh
python script.py urls.txt -i 120  # Check every 2 minutes
```
Add More URLs
Edit urls.txt to add more websites.

## 🏗️ Contributing
Contributions are welcome!

Fork the repo

Create a new branch: git checkout -b feature-name

Commit changes: git commit -m "Added new feature"

Push and create a PR!

## ⭐ Support
If you found this useful, please star the repo ⭐ and share it!
For issues or suggestions, open a GitHub issue.



