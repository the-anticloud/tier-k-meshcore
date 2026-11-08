# Deploy Guide — K_MESHCORE
**Tier:** TIER_8_RF_MESH_DEFENSE | **Stack:** Python 3.11, pyloralib, PAX 27B, AIOSS_FORMAT
**Air-gap capable after initial setup.**

## Prerequisites
Python 3.11+, pyloralib 0.x. LoRa transceiver (SX1276/SX1278) or simulator. 4GB RAM.

## Environment
LoRa hardware (SX1276-based module, Raspberry Pi with LoRa HAT) or software simulator. Low power. 4GB RAM.

## AIOSS Integration
```bash
aioss init --module K_MESHCORE --output ./k_meshcore.aioss
aioss append --chain ./k_meshcore.aioss --payload ./output.bin --module K_MESHCORE
aioss verify --chain ./k_meshcore.aioss
```

## Air-Gap Setup
```bash
pip download -r requirements.txt -d ./wheels/
pip install --no-index --find-links ./wheels/ -r requirements.txt
```

## PAX 27B Harness Wiring
```python
from anticloud_pax import PAXHarness
harness = PAXHarness(
    model_path="./pax-27b-q4.gguf",
    module="K_MESHCORE",
    aioss_chain="./K_MESHCORE.aioss",
    classification="L5_NARROW_L2_GENERAL"
)
result = harness.process(input_data)
```

## Verification
```bash
aioss verify --chain ./K_MESHCORE.aioss --verbose
python -m K_MESHCORE.tests.smoke
```
