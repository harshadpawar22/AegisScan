# 🛡️ AegisScan

**AI-Assisted Vulnerability Assessment & Penetration Testing Tool**

Meet AegisScan: your open-source security guardian. By fusing elite penetration tools with a sharp AI brain, it transforms messy scans into a masterclass in defense. Whether you're a curious beginner or a seasoned pro, AegisScan automates the grunt work and delivers the "Aha!" moments through effortless, intelligent analysis.

## 🔧 Features

| Category | Features |
|----------|----------|
| ✅ **Reconnaissance** | Subdomain finder, WHOIS lookup, port scanning, DNS enumeration |
| 🧠 **AI Assistant** | Interprets scan results, suggests next steps, explains findings |
| 🚀 **Automation** | Automated comprehensive scans via CLI or web interface |
| 📊 **Reports** | Generates professional PDF and HTML reports |
| 👥 **Multi-user** | Team collaboration with project management and audit logs |
| 🎯 **Learning Mode** | Educational explanations for students and beginners |
| ☁️ **API Ready** | RESTful API for integration and automation |
| 🔒 **Security** | Rate limiting, authentication, and secure configurations |

## 🚀 Quick Start

### Prerequisites

- Python 3.8+ and pip
- Node.js 16+ and npm
- nmap, dnsutils, whois (installed automatically)

### Installation

```bash
# Clone the repository
git clone https://github.com/harshadpawar22/AegisScan.git
cd AegisScan

# Run the installation script (Ubuntu/Debian)
chmod +x scripts/install.sh
./scripts/install.sh

# Or install manually:
# Backend setup
cd backend
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Frontend setup
cd ../frontend
npm install

# CLI setup
cd ../cli
pip3 install -r requirements.txt
chmod +x AegisScan.py
```

### Configuration

```bash
# Copy and edit environment file
cp .env.example .env
# Edit .env with your settings (API keys, database config, etc.)
```

### Running AegisScan

**Start the Backend API:**
```bash
cd backend
source venv/bin/activate
python app.py
# API available at http://localhost:5000
```

**Start the Frontend (new terminal):**
```bash
cd frontend
npm start
# Web interface at http://localhost:3000
```

**Use the CLI:**
```bash
# Add to PATH or use directly
./cli/AegisScan.py --help

# Example scans
AegisScan subdomain example.com
AegisScan port 192.168.1.1 --port-range 1-1000
AegisScan vuln https://example.com --scan-type web
```

## 📖 Usage Examples

### Web Interface

1. **Dashboard**: View scan statistics, recent results, and quick actions
2. **Scanner**: Configure and run different types of security scans
3. **Results**: Analyze findings with AI-powered insights
4. **Reports**: Generate professional security assessment reports
5. **AI Assistant**: Chat with AI for security advice and explanations

### Command Line Interface

```bash
# Comprehensive subdomain enumeration
AegisScan subdomain target.com --output results.json

# Port scan with custom range
AegisScan port 10.0.0.1 --port-range 1-65535

# Web application vulnerability assessment
AegisScan vuln https://target.com --scan-type comprehensive

# DNS reconnaissance
AegisScan dns target.com

# Generate professional report
AegisScan report results.json --format pdf
```

### API Usage

```python
import requests

# Start a subdomain scan
response = requests.post('http://localhost:5000/api/scan/subdomain', 
                        json={'domain': 'example.com'})
result = response.json()

# Get AI analysis
ai_response = requests.post('http://localhost:5000/api/ai/chat',
                           json={'message': 'Explain this vulnerability', 
                                'context': result})
```

## 🏗️ Architecture

AegisScan follows a modular architecture:

```
AegisScan/
├── backend/          # Python Flask API server
│   ├── app.py       # Main application
│   ├── modules/     # Scanning and AI modules
│   └── models/      # Database models
├── frontend/         # React web interface
│   ├── src/
│   └── components/
├── cli/             # Command-line interface
├── reports/         # Generated reports
├── docs/           # Documentation
└── scripts/        # Installation and utility scripts
```

### Key Components

- **Reconnaissance Module**: Subdomain enumeration, port scanning, DNS/WHOIS lookups
- **AI Assistant**: OpenAI integration for intelligent analysis and recommendations
- **Vulnerability Scanner**: Web app and network service security assessment
- **Report Generator**: Professional PDF/HTML report creation
- **Multi-user System**: Authentication, projects, and audit logging

## 🔍 Scan Types

### 1. Subdomain Enumeration
- Brute force common subdomains
- Certificate Transparency log search
- DNS zone transfer attempts
- AI analysis of discovered subdomains

### 2. Port Scanning
- TCP/UDP port discovery
- Service version detection
- Operating system fingerprinting
- Risk assessment of open services

### 3. Vulnerability Assessment
- Web application security testing
- Network service vulnerability detection
- SSL/TLS configuration analysis
- Security header verification

### 4. DNS Enumeration
- A, AAAA, MX, NS, TXT record collection
- DNS zone information gathering
- Email server discovery
- Infrastructure mapping

### 5. WHOIS Lookup
- Domain registration information
- Ownership and contact details
- Name server identification
- Expiration date monitoring

## 🤖 AI Features

AegisScan integrates AI to enhance security assessments:

- **Intelligent Analysis**: Automatically interprets scan results
- **Risk Assessment**: Prioritizes findings by severity and impact
- **Remediation Guidance**: Provides specific fix recommendations
- **Learning Mode**: Explains techniques for educational purposes
- **Contextual Chat**: Interactive AI assistant for security questions

## 📊 Reporting

Generate professional security reports in multiple formats:

- **HTML Reports**: Interactive web-based reports with charts
- **PDF Reports**: Professional documents for stakeholders
- **JSON Exports**: Machine-readable data for integration
- **Executive Summaries**: High-level findings for management

## 🔐 Security Considerations

**Important**: AegisScan is designed for authorized security testing only.

- Only scan systems you own or have explicit permission to test
- Some scans may be detected by security systems
- Follow responsible disclosure practices
- Respect rate limits and target system resources
- Review local laws and regulations before testing

### Development Setup

```bash
# Clone and setup development environment
git clone https://github.com/harshadpawar22/AegisScan.git
cd AegisScan

# Install development dependencies
pip install -r backend/requirements-dev.txt
npm install --dev --prefix frontend

# Run tests
pytest backend/tests/
npm test --prefix frontend
```

## ⚠️ Disclaimer

AegisScan is for educational and authorized testing purposes only. Users are responsible for complying with applicable laws and obtaining proper authorization before scanning any systems. The developers assume no liability for misuse of this tool.

---

**Made with ❤️ by Harshad Pawar for the cybersecurity community**
