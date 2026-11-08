# Developer Cookbook — K_MESHCORE
**Stack:** Python 3.11, pyloralib, PAX 27B, AIOSS_FORMAT
**Domain:** MeshCore: LoRa mesh network protocol for Anticloud distributed sensor networks

## LoRa mesh receive and analyze
```python
from k_meshcore import MeshCoreGateway

gateway = MeshCoreGateway(
    lora_port="/dev/ttyUSB0",
    frequency_hz=868_000_000,  # EU868
    pax_model="./pax-27b-q4.gguf",
    aioss_chain="./meshcore.aioss"
)

gateway.start()
for msg in gateway.messages():
    print(f"Node {msg.node_id}: {msg.payload}")
    if msg.anomaly_score > 0.8:
        alert = gateway.pax_alert(msg)
        print(f"PAX alert: {alert}")
```

## Send downlink command
```python
gateway.send(node_id=7, command="set_sample_rate", value=60)
```

## AIOSS Chain Append
```python
import hashlib, time

def aioss_append(chain_path, payload: bytes, module_id: str):
    entry_hash = hashlib.sha3_256(payload).digest()
    ts = int(time.time_ns()).to_bytes(8, 'big')
    with open(chain_path, 'rb') as f:
        f.seek(-32, 2); prev_hash = f.read(32)
    new_hash = hashlib.sha3_256(prev_hash + entry_hash + ts).digest()
    with open(chain_path, 'ab') as f:
        f.write(ts + entry_hash + new_hash)
    return new_hash.hex()
```
