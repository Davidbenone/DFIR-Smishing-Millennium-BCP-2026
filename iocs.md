# Indicators of Compromise and Investigation

[Back to main README](README.md)

Indicators are defanged to reduce accidental navigation. These observations are contextual to the investigation and may change over time.

| Type | Defanged indicator | Context | Confidence / caveat |
| --- | --- | --- | --- |
| URL | `hxxps://millennium[.]analisar-pt[.]com/` | Destination advertised by the suspicious SMS | High confidence as the investigated URL; not an attribution claim |
| Domain | `millennium[.]analisar-pt[.]com` | Millennium BCP impersonation | High confidence as the observed suspicious hostname |
| IP address | `104[.]21[.]59[.]220` | Observed in investigation context | Shared infrastructure; do not attribute solely on this basis |
| Delivery | SMS / smishing | Claimed pending EUR 1,472 transfer | Observed social engineering pretext |
| Collection targets | Name, mobile phone, Portuguese NIF | Fields displayed in the inspected interface | Screens inspected by local DOM visibility changes |
| Code behavior | Telegram Bot API transmission routines | Identified in JavaScript source | Intended functionality; successful exfiltration unconfirmed |

## Detection and investigation notes

- Treat a bank-branded SMS linking to a non-official domain as a phishing investigation lead.
- Correlate domains and IP addresses with timestamps and independent evidence before making blocking or attribution decisions.
- An IP on shared infrastructure is not a unique indicator of the phishing operator.
- The presence of an API endpoint in JavaScript is not proof of a completed transmission.
- Avoid sharing live bot credentials, chat IDs or unredacted source code.

## Scope of conclusions

The case supports an assessment of a smishing attempt impersonating Millennium BCP with a phishing-themed interface. It does **not** demonstrate successful data exfiltration, compromise of bank systems or financial losses.

## Related material

- [Methodology](methodology.md)
- [Network analysis](network-analysis.md)
- [Public DFIR report](Relatorio_DFIR_Public_EN.pdf)
