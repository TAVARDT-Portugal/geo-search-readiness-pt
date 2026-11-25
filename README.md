# Auditor de Pesquisa com IA e GEO

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Pesquisa%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/pt/auditor-pesquisa-ia-geo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Auditor CLI de Generative Engine Optimization (GEO) para inspeção de crawlers de IA, dados estruturados Schema.org e extracao de conhecimento.

Desenvolvido e mantido pela divisao de engenharia de pesquisa semantica da **TAVARDT Portugal**.

***

## Capacidades de Auditoria GEO

* **Acesso de Robots de IA**: Inspeção de diretivas em `robots.txt` para rastreadores como GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot e Google-Extended.
* **Extracao de Entidades Semanticas**: Verificacao da presenca de dados estruturados Schema.org em formato JSON-LD.
* **Sinais Semanticos Fundamentais**: Validacao de titulos H1 e meta descriptions para indexacao precisa por modelos de linguagem.
* **Pontuacao de Prontidao**: Diagnostico tecnico de 0 a 100 pontos com passos claros de correcao.

***

## Instalação e Execucao

Requer Python 3.8 ou superior, utilizando exclusivamente a biblioteca padrao.

```bash
git clone https://github.com/TAVARDT-Portugal/geo-search-readiness-pt.git
cd geo-search-readiness-pt
python geo_auditor.py empresa.pt
```

Para gerar a saída em formato JSON:

```bash
python geo_auditor.py empresa.pt -json
```

***

## Diagnostico Completo na Web

Para auditorias continuas de prontidao para motores generativos, utilize a ferramenta oficial:

* **Auditor de Pesquisa com IA e GEO**
* **[Portal Corporativo TAVARDT](https://ag.tavardt.com/pt/)**

***

## Consultoria em Motores de IA e Semantica

Para projetos de estruturacao semantica e presenca em agentes autonomos em Portugal, contacte a equipa da **TAVARDT Portugal**.

***



## Links Úteis

* **Portal Corporativo:** https://ag.tavardt.com/pt/
* **Suíte de Diagnósticos:** https://tools.tavardt.com/pt/
* **Contacto Técnico:** https://ag.tavardt.com/pt/contacto/

***

### Licença
Distribuído sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para obter detalhes completos.

***

© 2026 TAVARDT. All rights reserved.
