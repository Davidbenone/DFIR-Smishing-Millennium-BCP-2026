# DFIR Investigation: Millennium BCP Impersonation Smishing (Portugal, 2026)

> Independent security investigation for defensive and educational purposes. Not affiliated with Millennium BCP.

## Executive summary

On **9 November 2026**, an SMS displayed as sent by “MILLENNIUM” claimed that a **EUR 1,472** bank transfer was pending and directed the recipient to a suspicious website. Four website screens were examined. They presented a purported fraud prevention process and requested a name, mobile phone number and Portuguese taxpayer identification number (NIF).

The JavaScript source contained functions designed to transmit collected data using the Telegram Bot API. **Actual data exfiltration to Telegram was not demonstrated.**

## Defanged indicators of compromise

| Type | Indicator |
| --- | --- |
| Suspicious URL | `hxxps://millennium[.]analisar-pt[.]com/` |
| Observed IP | `104[.]21[.]59[.]220` (shared infrastructure; attribution not established) |
| Delivery method | SMS / smishing |
| Impersonated institution | Millennium BCP |

Do not browse the suspicious website outside a controlled analysis environment.

## Investigation environment and methods

- VirtualBox virtual machine and OPNsense firewall.
- Firefox Developer Tools for HTML, JavaScript and DOM inspection.
- Wireshark for network capture review.
- SingleFile HTML preservation and evidence screenshots.
- SHA-256 hashes for source evidence integrity checks.

The four website screens were inspected by **locally changing DOM element visibility**. No real personal information was entered and no forms were deliberately submitted. Displaying a hidden screen does **not** prove that the website's full interaction flow was executed.

## Findings and limitations

- A suspicious banking themed interface requested personal data.
- JavaScript contained routines intended to send information to Telegram.
- QUIC traffic associated with an IP observed during the investigation was captured.
- **Not confirmed:** successful Telegram exfiltration, operator identity, SMS sender authenticity, number of victims or banking losses.

## Reports and evidence

- [Public DFIR report (English)](Relatorio_DFIR_Public_EN.pdf)
- [Public DFIR report (Portuguese)](Relatorio_DFIR_Publico_VirusTotal_PT_PT.pdf)

Report links will work after the corresponding PDFs are uploaded. Only sanitized images and evidence derivatives should be published.

Never upload the confidential report, raw packet captures, bot token, Telegram chat ID, or unredacted source code.

## Researcher

VirusTotal public comments: [DavidB3_1](https://www.virustotal.com/gui/user/DavidB3_1/comments).

## References

ISO/IEC 27037, ISO/IEC 27035, and Regulation (EU) 2016/679 (GDPR).

## Responsible disclosure

This project distinguishes direct observations from technical interpretation and unproven hypotheses. Indicators are defanged to reduce accidental navigation to malicious infrastructure.

[Versão em português](README_PT.md)
