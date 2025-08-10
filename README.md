# IMSI & TMSI Scanner GUI

A **Tkinter-based** SDR control panel for scanning GSM frequencies to detect IMSIs and map TMSIs in real time.  
Built for lawful research, educational use, and SDR experimentation.

---

## Features
- **Multi-frequency scanning**
- **Multiple IMSI targets** (comma- or line-separated)
- **TMSI Attach mapping** (IMSI ↔ TMSI detection)
- CSV export of results
- Async non-blocking capture (UI stays responsive)

---

## Requirements

### Hardware
- SDR device (HackRF, USRP, RTL-SDR, etc.)
- GSM-band antenna

### Software
- Python 3.8+
- `tshark` (Wireshark CLI)
- GNU Radio / UHD (for USRP)
- Python packages:
  ```bash
  pip install -r requirements.txt
  ```

---

## Installation
```bash
git clone https://github.com/Eylonk14/2GMaster.git
cd 2GMaster
pip install -r requirements.txt
```

Make sure `tshark` works:
```bash
tshark -v
```

---

## Running
**⚠ Root access is required** to use SDR hardware & capture packets.

```bash
sudo python3 2gmaster.py
```

---

## Usage

### IMSI Scan Tab
1. Enter one or more IMSIs (comma-separated or one per line).
2. Select GSM frequencies to monitor.
3. Click **Start Scan** to begin.
4. Matches are logged in the text area.

### TMSI Attach Tab
1. Choose CSV output location (or use default).
2. Click **Start TMSI Capture**.
3. The system listens for:
   - *Location Updating Accept*
   - *TMSI Reallocation Command*
4. Captured IMSI↔TMSI mappings are appended to CSV.

---

## Legal Notice
Intercepting GSM traffic may be **illegal** in your jurisdiction without authorization.  
Only use in controlled lab/test environments.

---

## Example Command
Run IMSI scan on multiple targets:
```text
IMSI Numbers:
  123456789012345
  234567890123456
```

---

## License
MIT License
