# Mineração Longitudinal da Legislação Federal Brasileira (1850 - 2026)
Este repositório contém um ecossistema desenvolvido em R para extração, processamento, análise temporal e mineração de texto da produção normativa federal brasileira em um horizonte longitudinal de 176 anos (1850 a 2026).

O sistema realiza uma escavação arqueológica na linguagem do Estado, mapeando os ciclos taxonômicos, os apagamentos administrativos e as transições semânticas na proteção e regulação de três grupos sociais historicamente vulnerabilizados: Idosos, Pessoas com Deficiência e a População em Situação de Rua.

🚀 Arquitetura e Recursos do Pipeline
O script foi desenhado sob critérios e engenharia de dados e ciência de dados preditiva, apresentando:

Web Scraping Histórico Estável: Captura automatizada de atos normativos de relevância histórica (desde o Império e a República Velha) diretamente dos repositórios estáveis da Presidência da República.

Consumo Automatizado da API de Dados Abertos: Integração robusta via httr2 para mineração em lote de bases anuais da Câmara dos Deputados (1930 a 2026).

Proteção Contra Colunas Fantasmas: Tratamento defensivo de dados dinâmicos fora de estruturas mutáveis ordinárias, garantindo a integridade do pipeline contra descontinuidades de esquemas (schema drift).

Filtro Temático Baseado em Regex Histórico: Mapeamento semântico que abrange desde termos arcaicos e estigmatizantes (ex: defeito physico, vadiagem, indigente, alienado) até as taxonomias contemporâneas de direitos.

Métrica de TF-IDF Normalizado por Super-Documentos Decadais: Engenharia de atributos construída para concatenar os textos por blocos de dez anos, neutralizando o viés volumétrico do presente e forçando a emersão de raridades documentais sufocadas no passado burocrático.

📁 Estrutura de Diretórios Gerada
O sistema gerencia de forma autônoma a persistência e o ciclo de vida dos arquivos na seguinte árvore de diretórios:

Plaintext
projeto_legislativo/
├── brutos/
│   ├── historicos/      # Resíduos e HTMLs de atos antigos
│   └── modernos/        # Downloads temporários de CSVs da API
├── processados/         # Arquivos binários indexados (.rds) por ano
├── log_erros.txt        # Monitoramento e auditoria de falhas de rede/estrutura
├── corpus_consolidado_1850_2026.csv   # O dataset final unificado
└── grafico_tfidf_normalizado.png       # Plot de alta resolução (300 DPI)

🛠️ Pré-requisitos e Dependências
O gerenciamento de pacotes é realizado de forma automática pelo pacman. Para rodar o script, certifique-se de ter o R instalado em sua máquina. As dependências utilizadas são:

tidyverse (Manipulação e estruturação de dados em formato tidy)

httr2 (Requisições HTTP resilientes)

rvest (Raspagem de páginas HTML da Presidência)

tidytext & tm (Mineração de texto, tokenização e cálculo do TF-IDF)

fs & pdftools (Gerenciamento seguro de arquivos e leitura de PDF)

💻 Como Executar
Clone este repositório em sua máquina:

Bash
git clone https://github.com/seu-usuario/nome-do-repositorio.git
Abra o arquivo do script no RStudio.

Altere a linha inicial indicando o seu diretório de trabalho:

R
setwd("seu caminho para o diretório de trabalho")
Execute o script completo. O pipeline limpará tentativas quebradas anteriores, disparará as requisições respeitando as políticas de politeness (Sys.sleep), consolidará o corpus e exportará as visualizações automáticas.

📊 Outputs Gerados
1. Evolução Temporal da Produção Legislativa
Geração de um gráfico de linhas contínuo utilizando o parâmetro atualizado linewidth, que segmenta a densidade de atos ano a ano, revelando as fraturas normativas e os limiares de visibilidade institucional dos três grupos ao longo de quase dois séculos.

2. Painel Expandido de Palavras-Chave (TF-IDF)
Exportação de uma matriz gráfica em formato PNG de alta resolução (18cm x 24cm, 300 DPI). O gráfico agrupa o Top 5 de termos por década, revelando o funcionamento profundo do Estado como banco central do capital simbólico e denunciando o filtro ideológico de cada ciclo político — como a transmutação corporativo-militar da velhice e da deficiência na era do Estado desenvolvimentista (1930-1970).

📝 Licença
Este projeto está licenciado sob a Licença MIT. O script é parte integrante da tese de doutorado de Hernany Gomes de Castro. A reprodução é autorizada, desde que citada a fonte.
