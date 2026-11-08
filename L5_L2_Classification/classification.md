# L5 Narrow / L2 General Classification — K_MESHCORE
**Platform:** Anticloud | **Tier:** TIER_8_RF_MESH_DEFENSE | **PAX:** 27B
**IP:** USPTO pending 2026, Anticloud FZ LLE, 0-1.gg | **License:** Apache-2.0

## L5 Narrow
K_MESHCORE implements LoRa/LoRaWAN mesh networking for Anticloud distributed deployments: device registration, mesh routing, adaptive data rate (ADR), and AIOSS-chained message logs. Narrow scope: Anticloud LoRa mesh for TIER_9 IoT sensors and TIER_8 tactical mesh.

## L2 General
L2 General: K_MESHCORE provides low-power wide-area mesh for any Anticloud tier deploying in areas without Wi-Fi or cellular. TIER_9 agricultural sensors and TIER_8 battlefield mesh both use K_MESHCORE.

## PAX 27B Integration
PAX 27B processes mesh telemetry: aggregating sensor readings from multiple mesh nodes and generating structured alerts for the Anticloud core. 'Node 7 shows temperature outlier — likely sensor fault or fire event.'

## AIOSS Audit Chain
Every mesh event (node ID hash + message payload hash + RSSI + SNR + routing path hash) is chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Offline-verifiable, tamper-evident, zero cloud dependency.

## Regulatory / Compliance
FCC Part 15 (unlicensed radio). LoRaWAN 1.0.4 specification. IEC 62443-4-2 (IoT).
