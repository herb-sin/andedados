Monitoramento da Qualidade da água das praias da cidade de Praia Grande
Este projeto tem como objetivo automatizar a coleta de dados sobre a qualidade da água das praias de Praia Grande, disponibilizados pela CETESB (Companhia Ambiental do Estado de São Paulo), e transformá-los em um formato estruturado para análise.

📌 Visão Geral
O projeto utiliza técnicas de web scraping e requisições HTTP para extrair dados da plataforma ArcGIS da CETESB, que monitora a balneabilidade das praias do litoral paulista. Os dados são processados e salvos em um arquivo CSV, permitindo análises temporais e a geração de insights sobre a qualidade da água.

🛠️ Tecnologias Utilizadas
Python: Linguagem de programação principal.

Selenium: Automação de navegador para interação com a plataforma ArcGIS.

Requests: Biblioteca para fazer requisições HTTP à API da CETESB.

Pandas: Manipulação e análise de dados.

BeautifulSoup: Parsing de conteúdo HTML (usado como fallback).

Jupyter Notebook: Ambiente interativo para desenvolvimento e teste do código.

📋 Pré-requisitos
Antes de executar o projeto, certifique-se de ter instalado:

Python 3.10 ou superior.

Conda ou pip para gerenciamento de pacotes.

Google Chrome (ou outro navegador compatível com o Selenium).

🚀 Como Executar
1. Configurar o Ambiente
Clone o repositório e crie o ambiente Conda com as dependências necessárias:

bash
git clone [URL_DO_REPOSITÓRIO]
cd [NOME_DO_REPOSITÓRIO]
conda env create -f pgsea_env.yml
conda activate pgsea_env

2. Executar o Jupyter Notebook
Abra o Jupyter Notebook e execute o arquivo pgqa.ipynb:

bash
jupyter notebook

3. Passo a Passo no Notebook
O notebook está dividido em células que realizam as seguintes tarefas:

Importar Bibliotecas: Carrega todas as dependências necessárias.

Configurar o Navegador: Inicializa o Selenium e acessa o site da CETESB.

Identificar a API de Dados: Manualmente, usando as Ferramentas do Desenvolvedor (F12), identifique a URL da API que fornece os dados em JSON.

Coletar Dados via API: Faz uma requisição direta à API e processa os dados.

Salvar os Dados: Exporta os dados para um arquivo CSV (qualidade_agua_praia_grande.csv).

4. Resultados
Após a execução, o arquivo qualidade_agua_praia_grande.csv será gerado com os seguintes campos:

ID_Objeto, ID_Praia, ID_Municipio, Cod_Municipio_IBGE

Municipio, Praia, Classificacao_Agua (Própria/Imprópria)

Data_Amostra_Inicio, Data_Atualizacao_Sistema

UGRHI, Dist_Norte, Qualidade_Codigo

📊 Análise dos Dados
Os dados coletados podem ser utilizados para:

Monitoramento Contínuo: Agende a execução do script para atualizações periódicas (diárias/semanais).

Alertas: Envie notificações quando uma praia for classificada como "Imprópria".

Visualização: Crie dashboards ou gráficos para acompanhamento público.

📄 Exemplo de Saída
ID_Objeto	ID_Praia	Municipio	Praia	Classificacao_Agua	Data_Amostra_Inicio	Data_Atualizacao_Sistema
134	PGCF390	PRAIA GRANDE	CANTO DO FORTE	Imprópria	2025-05-11	2025-05-15 12:10:03.363
135	PGBO393	PRAIA GRANDE	BOQUEIRÃO	Imprópria	2025-05-11	2025-05-15 12:10:03.363
🤝 Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou enviar pull requests com melhorias.

📜 Licença
Este projeto está licenciado sob a licença MIT. Consulte o arquivo LICENSE para mais detalhes.

Nota: Este projeto foi desenvolvido para fins acadêmicos e de aprendizado. Certifique-se de respeitar os termos de uso da CETESB ao utilizar os dados coletados.
