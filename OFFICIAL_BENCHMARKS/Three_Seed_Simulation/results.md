# Three_Seed_Simulation — K_MESHCORE

**Run:** 2026-09-30T18:11:11.493145+00:00

```json
{
  "project": "K_MESHCORE",
  "seeds": [
    51320,
    82657,
    16856
  ],
  "seed_method": "sha256(name)[:8]+offsets[0,31337,65536]",
  "helm_standard": true,
  "run_ts": "2026-09-30T18:11:11.493145+00:00",
  "metrics": {
    "throughput_tokens_per_sec": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        76.291,
        50.125,
        1.852
      ],
      "mean": 42.756,
      "std": 30.833,
      "ci_95_low": -17.677,
      "ci_95_high": 103.189
    },
    "latency_p50_ms": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        60.883,
        85.475,
        13.906
      ],
      "mean": 53.421,
      "std": 29.69,
      "ci_95_low": -4.771,
      "ci_95_high": 111.613
    },
    "memory_mb": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        20.237,
        84.848,
        94.676
      ],
      "mean": 66.587,
      "std": 33.019,
      "ci_95_low": 1.87,
      "ci_95_high": 131.304
    },
    "accuracy_score": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        20.909,
        77.105,
        7.749
      ],
      "mean": 35.254,
      "std": 30.077,
      "ci_95_low": -23.697,
      "ci_95_high": 94.205
    },
    "f1_score": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        51.496,
        16.649,
        67.136
      ],
      "mean": 45.094,
      "std": 21.103,
      "ci_95_low": 3.732,
      "ci_95_high": 86.456
    },
    "inference_tps": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        81.426,
        47.974,
        55.865
      ],
      "mean": 61.755,
      "std": 14.278,
      "ci_95_low": 33.77,
      "ci_95_high": 89.74
    },
    "quality_score": {
      "seeds": [
        51320,
        82657,
        16856
      ],
      "values": [
        26.505,
        41.443,
        89.449
      ],
      "mean": 52.466,
      "std": 26.853,
      "ci_95_low": -0.166,
      "ci_95_high": 105.098
    }
  }
}
```
