# Investigation Methodology

[Back to main README](README.md)

## Scope

This case study examines an SMS impersonating Millennium BCP and the associated suspicious website. The objective was to document observable phishing indicators, inspect the page's client-side behavior and review available network evidence.

The investigation was conducted for defensive research and education. No attempt was made to authenticate to a bank, enter real personal information or deliberately submit the phishing forms.

## Analysis environment

| Component | Purpose |
| --- | --- |
| VirtualBox virtual machine | Controlled browser analysis |
| OPNsense | Network boundary and traffic observation |
| Firefox Developer Tools | DOM, HTML and JavaScript inspection |
| Wireshark | Review of captured network traffic |
| SingleFile | Preservation of HTML page content |
| Screenshots | Visual documentation of observed interfaces |

## Investigation workflow

1. **Initial triage:** Record the SMS pretext, claimed pending transfer and suspicious destination. Preserve the original message and publish only a suitable evidence derivative.
2. **Website inspection:** Inspect the phishing-themed interface in Firefox Developer Tools, without entering real personal or banking data.
3. **Screen documentation:** Reveal four interface states by changing DOM element visibility locally. This is a visual inspection technique, not proof that the site's normal workflow was executed.
4. **Source review:** Examine JavaScript for data collection and network transmission routines. Code designed to use the Telegram Bot API was identified.
5. **Network review:** Inspect captured traffic with Wireshark, including observed QUIC traffic. Distinguish transport observations from evidence of application-level data transfer.
6. **Reporting:** Document observations, indicators, limitations and sanitized screenshots. Keep confidential artifacts out of the public repository.

## Evidence interpretation

The existence of a Telegram transmission routine in source code indicates intended functionality; it does not establish that a message was sent or received. Likewise, a screen exposed by changing DOM styles does not establish that a victim progressed through that screen.

The observed network traffic does not prove Telegram exfiltration. No confirmed victim count, financial loss or threat actor identity is asserted.

## Handling and publication

The public repository contains sanitized derivatives and reporting material. Raw packet captures, unredacted HTML or JavaScript containing secrets, bot credentials, Telegram chat identifiers, real personal data and the confidential report should not be published.

Evidence hashes are useful for verifying specific preserved files, but a hash is meaningful only when paired with the exact artifact and acquisition context. Consult the public report for the documented evidence set.

## Limitations

- No deliberate form submission or use of real personal data.
- No confirmed end-to-end execution of the phishing workflow.
- No demonstrated successful Telegram exfiltration.
- No attribution to a specific operator.
- Observed IP addresses may belong to shared infrastructure and must not be treated as actor identifiers.

## Related material

- [Network analysis](network-analysis.md)
- [Indicators of compromise](iocs.md)
- [Public DFIR report](Relatorio_DFIR_Public_EN.pdf)
