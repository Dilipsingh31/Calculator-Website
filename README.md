# Web Application Security Assessment Project  
*Automated vulnerability detection, penetration testing, and log analysis for a financial services web app.*  

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Burp Suite](https://img.shields.io/badge/Tools-Burp_Suite-red)](https://portswigger.net/burp)
[![Metasploit](https://img.shields.io/badge/Tools-Metasploit-critical)](https://www.metasploit.com/)
[![OWASP](https://img.shields.io/badge/Methodology-OWASP_Top_10-green)](https://owasp.org/)

---

## 📌 Objective  
Identified security flaws (SQLi, XSS, RCE) in a financial web app pre-launch to prevent breaches involving sensitive payment data.  

## 🛠️ Tools & Methodology  
- **Frameworks**: OWASP Top 10, MITRE ATT&CK  
- **Tools**:  
  - Scanning: Nessus, Nmap  
  - Exploitation: Metasploit, SQLMap, custom Python scripts  
  - Log Analysis: Python (`Pandas`, `Elasticsearch`), ELK Stack  
- **Reporting**: Dradis, Jupyter Notebooks  

## 🧑💻 My Contributions  
### Tasks & Code Examples  
1. **Automated CSRF Token Bypass Testing**  
   - Developed a Python script to automate CSRF token extraction and bypass authentication flows.  
   - **Code Snippet**:  
     ```python  
     import requests  
     from bs4 import BeautifulSoup  

     def extract_csrf_token(url):  
         response = requests.get(url)  
         soup = BeautifulSoup(response.content, 'html.parser')  
         token = soup.find('input', {'name': 'csrf_token'}).get('value')  
         return token  
     ```  
   - *[Link to full script](scripts/csrf_bypass.py)*  

2. **Log Analysis for Brute-Force Detection**  
   - Built a Jupyter Notebook to analyze server logs using Pandas and flag brute-force attacks.  
   - **Sample Output**:  
     ```  
     [+] 15 brute-force attempts detected from IP 192.168.1.100 between 2023-07-01 14:00 - 14:30.  
     ```  
   - *[View notebook](notebooks/brute_force_analysis.ipynb)*  

3. **Vulnerability Reporting**  
   - Created a sample report template in Markdown (see [reports/findings.md](reports/findings.md)).  

## 📈 Outcomes  
- **15+ vulnerabilities** identified, including critical CVEs.  
- **40% reduction** in manual testing effort via automation.  
- Client’s SOC team adopted my log analysis script for real-time monitoring.  

---

## 🗂️ Repository Structure  
