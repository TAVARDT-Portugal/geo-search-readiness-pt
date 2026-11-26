<p align="center">
  <a href="https://ag.tavardt.com/pt/">
    <img src="https://ag.tavardt.com/img/tavardt-banner.png" alt="TAVARDT" width="1024" />
  </a>
</p>

# Auditor de Otimização para Motores Generativos (GEO)

[![Auditor GEO](https://img.shields.io/badge/TAVARDT-Pesquisa%20IA%20GEO-5b3cf5.svg)](https://tools.tavardt.com/pt/auditor-pesquisa-ia-geo/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Ferramenta de diagnóstico automatizado para Generative Engine Optimization (GEO) e Answer Engine Optimization (AEO), analisando o acesso de robots de IA, estruturas de dados Schema.org e contexto semântico.

O sistema examina propriedades web face às esteiras de geração aumentada por recuperação (RAG) presentes em plataformas como SearchGPT, Perplexity AI, Claude, Gemini e Apple Intelligence. Concebido sem dependências externas, executa nativamente na consola Python e em pipelines de conformidade técnica.

***

## Capacidades de Verificação GEO e Âmbito Algorítmico

A pesquisa tradicional focava-se no alinhamento de palavras-chave e ligação entre páginas. Os motores generativos atuais constroem respostas dinâmicas processando passagens textuais fundamentadas em grafos de dados estruturados e referências fidedignas.

* **Inspeção de Robots de IA**: Análise exaustiva das regras no `robots.txt` para agentes autónomos como GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot, Google-Extended e Applebot-Extended.
* **Extração de Entidades Estruturadas**: Validação de código Schema.org em formato JSON-LD (`application/ld+json`), permitindo aos LLMs contextualizar marcas e serviços sem ambiguidades.
* **Hierarquia Semântica e Âncoras Textuais**: Verificação de títulos H1 e preenchimento de meta descriptions para correta fragmentação de blocos de texto.
* **Avaliação Quantitativa de Prontidão GEO**: Índice algorítmico de 0 a 100 pontos categorizando o domínio em Alta Visibilidade, Visibilidade Moderada ou Acesso Condicionado.
* **Execução Limpa e Rápida**: Implementação dependente apenas da biblioteca padrão do Python, assegurando verificações sub-segundo em qualquer ambiente operativo.

***

## Matriz de Verificação e Pontuação GEO

<table>
  <thead>
    <tr>
      <th align="left">Dimensão Auditada</th>
      <th align="left">Ponderação</th>
      <th align="left">Regra de Validação Técnica</th>
      <th align="left">Impacto na Resposta e Citação por IA</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Disponibilidade do robots.txt</strong></td>
      <td>20 Pontos</td>
      <td>Resposta HTTP 200 válida no ficheiro /robots.txt.</td>
      <td>Assegura que os agentes de pesquisa leem de forma consistente as regras de indexação.</td>
    </tr>
    <tr>
      <td><strong>Permissões para Robots de IA</strong></td>
      <td>30 Pontos</td>
      <td>Inexistência de regras Disallow: / dirigidas aos robots de IA.</td>
      <td>Impede a exclusão do domínio dos índices de pesquisa conversacional dos LLMs.</td>
    </tr>
    <tr>
      <td><strong>Schema.org JSON-LD</strong></td>
      <td>30 Pontos</td>
      <td>Presença de blocos application/ld+json válidos no código HTML.</td>
      <td>Garante o reconhecimento inequívoco de entidades no grafo de conhecimento global.</td>
    </tr>
    <tr>
      <td><strong>Meta Description Textual</strong></td>
      <td>10 Pontos</td>
      <td>Etiqueta meta name=description preenchida no cabeçalho.</td>
      <td>Fornece um resumo conciso para a síntese rápida de resultados e citações em assistentes.</td>
    </tr>
    <tr>
      <td><strong>Título Semântico H1</strong></td>
      <td>10 Pontos</td>
      <td>Existência de elemento h1 que estabelece o assunto da página.</td>
      <td>Constitui a âncora contextual para os algoritmos de vetorização e divisão de passagens.</td>
    </tr>
  </tbody>
</table>

***

## Instalação e Guia de Execução Rápida

Requer Python 3.8 ou superior recorrendo unicamente a módulos da biblioteca padrão (`sys`, `re`, `json`, `ssl`, `argparse`, `urllib.request`). Não são necessárias instalações via pip.

Clone o repositório e execute a avaliação sobre um domínio específico:

```bash
git clone https://github.com/TAVARDT-Portugal/geo-search-readiness-pt.git
cd geo-search-readiness-pt
python geo_auditor.py exemplo.pt
```

Para extrair os resultados em formato estruturado JSON:

```bash
python geo_auditor.py exemplo.pt -j
```

Inspecione domínios fornecendo o protocolo completo:

```bash
python geo_auditor.py https://exemplo.pt -j
```

Exemplo de payload JSON obtido:

```json
{
  "domain": "exemplo.pt",
  "robots_txt_status": "Found (HTTP 200)",
  "blocked_bots": [],
  "has_schema_jsonld": true,
  "has_meta_description": true,
  "has_h1": true,
  "score": 100,
  "status": "AI-Search Ready (High Visibility)",
  "recommendations": []
}
```

Escalares de classificação técnica:

* **Pontuação 85 a 100**: Prontidão para Pesquisa IA (Alta Visibilidade). Acesso livre e marcações estruturadas completas.
* **Pontuação 50 a 84**: Visibilidade Moderada (Otimizações Necessárias). Barreiras parciais ou ausência de entidades Schema.org.
* **Pontuação 0 a 49**: Acesso Condicionado (Inconformidades Críticas Detectadas). Bloqueio formal de robots ou carência de semântica básica.

***

## Perguntas Frequentes (FAQ Técnico)

### De que modo o bloqueio do OAI-SearchBot ou PerplexityBot afeta a presença em respostas de IA?
O OAI-SearchBot e o PerplexityBot operam na recuperação de informação em tempo real para o ChatGPT Search e Perplexity. Ao bloquear estes agentes no robots.txt, as plataformas ficam impedidas de analisar e citar o conteúdo do domínio durante a resposta aos utilizadores.

### Qual o papel dos dados estruturados Schema.org JSON-LD na extração de entidades pelos LLMs?
Os modelos de inteligência artificial recorrem a grafos semânticos para ancorar declarações factuais. A marcação Schema.org JSON-LD entrega atributos estruturados de entidades e serviços sem ruído de layout, facilitando a inclusão em respostas geradas por IA.

### Como é calculado o resultado de 0 a 100 de prontidão para motores generativos?
O algoritmo atribui 20 pontos à disponibilidade do robots.txt, 30 pontos à ausência de restrições aos robots de IA, 30 pontos à presença de código Schema.org JSON-LD, 10 pontos à meta description e 10 pontos ao título H1, atingindo o máximo de 100 pontos.

### De que forma a ferramenta examina o código sem necessidade de carregar um browser completo?
O utilitário efetua pedidos HTTP GET com User-Agent próprio para `/robots.txt` e para o endereço principal. O processamento do texto é concretizado através de expressões regulares ágeis, entregando relatórios imediatos sem o overhead de browsers headless.

### Como podem as equipas de engenharia ligar este diagnóstico a pipelines de DevSecOps e CI/CD?
Ao utilizar o parâmetro `-j`, o script escreve dados JSON no standard output. Sistemas de integração contínua podem avaliar os campos `score` e `blocked_bots` através do jq, travando a publicação caso alterações acidentais criem regras de bloqueio no robots.txt.

***

## Consultoria em Modelação Semântica e Pesquisa IA

Para consultoria em dados estruturados, grafos de conhecimento e visibilidade em agentes de IA em Portugal, contacte os especialistas da **TAVARDT Portugal**.

***

## Links Úteis

* **Portal Corporativo:** https://ag.tavardt.com/pt/
* **Suíte de Diagnósticos:** https://tools.tavardt.com/pt/
* **Contacto Técnico:** https://ag.tavardt.com/pt/contacto/

***

### Licença
Distribuído sob a Licença MIT.

***

© 2026 TAVARDT. Todos os direitos reservados.
