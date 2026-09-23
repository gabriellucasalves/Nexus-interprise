# Caso TechCorp — CorpSync_Service

A **TechCorp** contratou a **Nexus** para investigar atividade suspeita ligada ao componente `CorpSync_Service`.

Este diretório registra a execução do serviço: o que foi preservado, o que foi observado, o diagnóstico (fato × hipótese) e o material de apresentação.

## Conclusão em uma frase

Caso **didático/controlado** na FLARE-VM, com indicadores correlacionáveis. Comunicação HTTP comprovada só em `127.0.0.1:8080`. **Não** há prova de C2 externo, nem de exfiltração de `Financeiro.xlsx`.

## Entregas

| Arquivo | O que é |
| --- | --- |
| [Nexus_Relatorio_Investigacao_Forense_TechCorp.pdf](Nexus_Relatorio_Investigacao_Forense_TechCorp.pdf) | Relatório técnico (pitch da Nexus + perícia) |
| [Nexus_Cadeia_de_Custodia.pdf](Nexus_Cadeia_de_Custodia.pdf) | Cadeia de custódia do exame |
| [Nexus_Apresentacao_Caso_TechCorp_Ajustada_Final.pptx](Nexus_Apresentacao_Caso_TechCorp_Ajustada_Final.pptx) | Apresentação UNICEPLAC ajustada (versão final) com evidências |
| [Nexus_Colas_Apresentacao.pdf](Nexus_Colas_Apresentacao.pdf) | Colas de fala de cada integrante |

## O que foi observado

- `31/08/2026` — eventos do caso. `07/09/2026` — exame da Nexus.
- `08:41:12` — `CorpSync_Service` inicia; usuário `analyst`.
- `08:43:27` — registro de tentativa de acesso a `Financeiro.xlsx`.
- `08:44:18` — endpoint `192.168.56.20:8080` configurado no artefato.
- `08:44:22` — requisição de teste; User-Agent `CorpSync-Lab/4.2.1`.
- Wireshark: `GET /api/v1/sync` em `127.0.0.1:8080`, resposta `200 OK`.
- O fonte `CorpSync_Service.c` só imprime indicadores (sem socket).

## Funções neste caso

| Integrante | Função |
| --- | --- |
| Gabriel Lucas Alves da Silva | Gestão / liderança |
| Thiago Costa Renovato | Aquisição e preservação |
| Wesley Thiago Matias Xavier | Análise forense (execução) |
| Samer Osama Mohammad Taleeb | Análise forense (revisão cruzada) |
| Matheus Nascimento Cardoso | Sistemas e ferramentas |
| Bianca Xavier de Oliveira | Documentação e relatório |
| Isabela Rosa Dos Santos Gontijo | Revisão e qualidade |

Exercício encerrado. Andamento no quadro da Nexus: [Nexus — Quadro do projeto](https://gabriellucasalves.github.io/Nexus-interprise/).
