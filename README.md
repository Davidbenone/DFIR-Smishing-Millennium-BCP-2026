# DFIR — Smishing com personificação do Millennium BCP (Portugal, 2026)

> Investigação independente para fins defensivos e educativos. Sem afiliação com o Millennium BCP.

## Resumo executivo

Em **9 de novembro de 2026**, foi recebida uma SMS apresentada como «MILLENNIUM», alegando uma transferência pendente de **1 472 €** e encaminhando para um domínio suspeito. A análise identificou quatro ecrãs de um website que solicitava nome, telemóvel e NIF, utilizando uma narrativa de validação antifraude.

O JavaScript analisado contém lógica concebida para enviar informação à API de bots do Telegram. **Não foi demonstrada exfiltração efetiva para o Telegram.**

## Indicadores de compromisso (neutralizados)

| Tipo | Indicador |
| --- | --- |
| URL | `hxxps://millennium[.]analisar-pt[.]com/` |
| Vetor | SMS / smishing |
| Personificação | Millennium BCP |

**Não visitar o endereço suspeito fora de ambiente de análise controlado.**

## Metodologia e ambiente

- Máquina virtual VirtualBox, firewall OPNsense, Firefox Developer Tools e Wireshark.
- Inspeção de HTML e JavaScript, capturas de ecrã e análise de tráfego.
- Os quatro ecrãs do website foram observados por alteração **local** da visibilidade dos elementos DOM.
- Não foram introduzidos dados pessoais reais nem submetidos deliberadamente formulários.

A manipulação visual do DOM **não equivale** à execução do fluxo funcional do website.

## Resultados e limitações

- Evidência de uma interface destinada à recolha de dados pessoais sob pretexto bancário.
- Código com mecanismo de envio para a API do Telegram.
- Tráfego QUIC observado para infraestrutura associada ao domínio investigado.
- **Não confirmado:** envio efetivo para o Telegram, identidade real dos operadores ou autenticidade do remetente SMS.

## Relatório público

O relatório PDF sanitizado, `Relatorio_DFIR_Publico_VirusTotal_PT_PT.pdf`, está preparado para publicação separada após revisão final. Ainda não está anexado neste repositório.

**Não publicar:** relatório confidencial, PCAPs brutos, token de bot, Chat ID, HTML/JavaScript original com segredos ou imagens não sanitizadas.

## Referenciais

ISO/IEC 27037; ISO/IEC 27035; Regulamento (UE) 2016/679 (RGPD).

## Divulgação responsável

Todos os indicadores nesta página estão neutralizados (*defanged*). O objetivo é partilhar metodologia e resultados de investigação, distinguindo observações, inferências e factos não demonstrados.

## Perfil VirusTotal

- **Investigador:** [DavidB3_1 - comentários públicos no VirusTotal](https://www.virustotal.com/gui/user/DavidB3_1/comments)

Este perfil é indicado pelo autor da investigação. A ligação não implica que o VirusTotal tenha validado as conclusões deste relatório.
