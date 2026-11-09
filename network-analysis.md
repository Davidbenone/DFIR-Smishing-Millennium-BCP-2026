# Network Analysis

[Back to main README](README.md)

## Objective

Review available network observations from the controlled investigation of the Millennium BCP impersonation website, while avoiding unsupported claims about encrypted traffic or data exfiltration.

## Collection and inspection

The investigation used an analysis virtual machine, OPNsense and Wireshark. The public evidence gallery contains three sanitized Wireshark screenshots:

1. [Wireshark capture 1](06_wireshark_captura_1_sanitizada.png)
2. [Wireshark capture 2](07_wireshark_captura_2_sanitizada.png)
3. [Wireshark capture 3](08_wireshark_captura_3_sanitizada.png)

These are screenshots of observations, not a substitute for the original packet capture or a complete protocol reconstruction.

## Documented observations

| Area | Observation | Interpretation and limitation |
| --- | --- | --- |
| Network tooling | OPNsense and Wireshark used during analysis | Supports a controlled collection and review workflow |
| Transport | QUIC traffic was observed | QUIC traffic alone does not identify the application payload |
| Observed IP | `104[.]21[.]59[.]220` | Shared infrastructure; not evidence of operator identity |
| Website source | JavaScript included Telegram Bot API transmission functionality | Source-code intent does not prove a network request succeeded |
| Exfiltration | No successful Telegram exfiltration demonstrated | Do not infer successful transfer from code or encrypted packets |

## What the evidence does not establish

The available public observations do not confirm that personal information was sent to Telegram, received by an operator, or stored remotely. They also do not establish the identity of the site's operator or the number of affected users.

Avoid interpreting an IP associated with shared infrastructure as a unique attacker endpoint.

## Reproducibility and evidence policy

The public repository intentionally does not distribute raw PCAP/PCAPNG files or confidential artifacts. Review the sanitized screenshots and [public DFIR report](Relatorio_DFIR_Public_EN.pdf) for the published observations.

## Related material

- [Methodology](methodology.md)
- [Indicators of compromise](iocs.md)
