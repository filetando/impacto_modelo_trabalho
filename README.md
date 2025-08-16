# **O Cabo de Guerra Estratégico que Define o Futuro do Trabalho**

#### O cenário profissional pós-pandemia se transformou em um verdadeiro campo de batalha, com um cabo de guerra sendo travado entre duas visões de futuro: de um lado, empresas que defendem o retorno ao escritório como pilar para a cultura e a inovação; de outro, uma força de trabalho que, após experimentar a autonomia, agora valoriza a flexibilidade como um componente não negociável de sua carreira. Para os profissionais de dados no Brasil, essa discussão vai muito além de uma simples preferência de estilo de vida — tornou-se um fator decisivo para a satisfação, produtividade e, crucialmente, para a permanência em um emprego.

#### Ignorar essa tensão é um risco que nenhuma empresa pode se dar ao luxo de correr. A grande questão não é mais se a flexibilidade é importante, mas sim qual o custo de não oferecê-la. Esta análise se propõe a responder a essa pergunta com dados, não com opiniões. Utilizando o abrangente dataset "State of Data Brazil 2024/2025", vamos mergulhar fundo para quantificar a lacuna entre o modelo de trabalho que os profissionais de dados possuem atualmente e aquele que consideram ideal.

#### Nosso objetivo é claro: transformar um debate subjetivo em uma análise de risco de negócio. Ao longo deste estudo, responderemos a três perguntas fundamentais:

* Qual é o tamanho real do desalinhamento entre a oferta e a demanda por modelos
de trabalho flexíveis no Brasil?
* Como esse desalinhamento impacta diretamente a satisfação dos profissionais?
* Qual é o risco de evasão de talentos que as empresas enfrentam ao impor políticas de retorno ao escritório?

#### Prepare-se para uma análise que revela não apenas o que os profissionais querem, mas as consequências estratégicas de suas escolhas para o futuro do mercado de dados no país.

# **0. Importação das Bibliotecas, Configuração dos Gráficos e Carregamento do DataSet**
Iremos usar a linguagem de programação Python, com as bibliotecas Pandas, MatplotLib e Seaborn.

Para garantir que os gráficos sejam visualmente atraentes e de fácil leitura, foram aplicadas algumas configurações de estilo utilizando as bibliotecas matplotlib.pyplot e seaborn. O objetivo dessas configurações é padronizar a aparência dos gráficos e melhorar a sua clareza.

Os dados utilizados nessa Análise foram da pesquisa de 2024-2025 do DataHackers, retirados do [Kaggle](https://www.kaggle.com/datasets/datahackers/state-of-data-brazil-20242025/data)

# **1. Preparação do Terreno.**

Antes de qualquer análise, precisamos garantir que nossos dados estejam limpos, padronizados e prontos para serem explorados. Nesta etapa, selecionamos as colunas de interesse, tratamos valores ausentes e criamos novas variáveis que serão cruciais para a nossa história.

As principais ações incluem:

* Seleção das colunas sobre modelo de trabalho (atual e ideal), satisfação e a atitude do profissional em caso de um retorno obrigatório ao presencial.
* Padronização das categorias de modelo de trabalho para garantir consistência.
* Conversão da coluna de satisfação (que está em formato TRUE/FALSE) para um formato numérico (1/0), o que nos permitirá calcular taxas de satisfação.

Total de respondentes válidos na análise: 4863

Primeiras 5 linhas abaixo:

|       | modelo_atual    | modelo_ideal    |   satisfeito_num |
|:------|:----------------|:----------------|-----------------:|
|     0 | 100% Remoto     | Híbrido         |                1 |
|     1 | 100% Presencial | 100% Presencial |                1 |
|     2 | 100% Presencial | Híbrido         |                0 |
|     3 | Híbrido         | Híbrido         |                1 |
|     4 | 100% Remoto     | Híbrido         |                1 |

# **2. O Cenário Atual vs. O Cenário Ideal - Quantificando a Lacuna**

Com os dados preparados, nossa primeira pergunta é: qual o tamanho do desalinhamento entre a realidade e o desejo dos profissionais? Um gráfico de barras comparativo nos dará uma visão clara e impactante dessa diferença.

![Comparativo: Modelo de Trabalho Atual vs. Ideal](https://github.com/filetando/impacto_modelo_trabalho/blob/main/images/comparativo_modelos_trabalho.png)

Este gráfico de barras comparativo mostra a distribuição dos modelos de trabalho atual e ideal entre os profissionais. Ele revela que, embora a maioria já trabalhe nos modelos Remoto (45.7%) e Híbrido (38.0%), a preferência para o cenário ideal se inclina ainda mais para a flexibilidade: o modelo Híbrido é o ideal para 52.1% e o 100% Remoto para 46.0%. A preferência por trabalhar 100% Presencial no cenário ideal é mínima (1.9%), contrastando com os 16.3% que trabalham presencialmente hoje. Isso evidencia que a grande maioria dos profissionais deseja flexibilidade, e há uma clara insatisfação com o modelo 100% presencial.

# **3. O Impacto na Satisfação e o Risco de Perder Talentos**

**Sabemos que existe um desalinhamento. Mas qual o seu custo? Vamos investigar duas frentes:**
* Satisfação: Profissionais que trabalham no modelo que desejam são mais satisfeitos?
* Retenção: Qual seria a reação dos profissionais que hoje atuam de forma remota ou híbrida se fossem forçados a retornar ao escritório em tempo integral?

![Taxa de Satisfação por Modelo de Trabalho Atual](https://github.com/filetando/impacto_modelo_trabalho/blob/main/images/taxa_satisfacao_modelo_trabalho.png)

Este gráfico demonstra uma clara relação entre o modelo de trabalho e a satisfação. Os profissionais que atuam no modelo 100% Remoto reportam a maior taxa de satisfação (75.0%), seguidos pelos que estão no modelo Híbrido (69.0%). Em contraste, a satisfação é significativamente menor entre aqueles que trabalham 100% Presencial (49.7%). Isso sugere que a flexibilidade está diretamente associada a níveis mais altos de satisfação no ambiente de trabalho.

![Reação a um Retorno Obrigatório ao Escritório (Profissionais em modelo Remoto/Híbrido)](https://github.com/filetando/impacto_modelo_trabalho/blob/main/images/reacao_retorno_obrigatorio.png)

Este gráfico de pizza apresenta um dado crucial para a retenção de talentos. Entre os profissionais que atualmente trabalham nos modelos remoto ou híbrido, a esmagadora maioria (83,1%) afirma que procuraria outra oportunidade de emprego caso fossem obrigados a retornar ao modelo 100% presencial. Apenas 16,9% declaram que aceitariam o retorno. Isso não é apenas uma preferência de estilo de vida; é um risco de negócio tangível, representando uma potencial perda massiva de talentos.

# **4. Um Olhar Detalhado sobre o Desalinhamento**

Para entender exatamente onde ocorrem as maiores divergências, podemos criar uma tabela de contingência (ou crosstab). Ela cruza o modelo de trabalho atual com o modelo ideal, mostrando o fluxo de preferências de forma detalhada.

![Matriz de Preferência](https://github.com/filetando/impacto_modelo_trabalho/blob/main/images/matriz_preferencia.png)

Estas matrizes detalham as transições de preferência entre os modelos de trabalho atual e ideal. A matriz em porcentagem (normalizada por linha) é particularmente esclarecedora: ela mostra que, mesmo entre aqueles que hoje trabalham 100% Presencial, a vasta maioria (73.4%) preferiria o modelo Híbrido, e uma parcela considerável (19.3%) preferiria o 100% Remoto. Para quem já está no Híbrido, a preferência é majoritariamente por manter o Híbrido (75.1%) ou migrar para o 100% Remoto (23.4%). Entre os 100% Remotos, a grande maioria deseja permanecer Remoto (74.4%). A preferência por retornar ao presencial é residual em todos os grupos.

# **Conclusão: A Flexibilidade como Fator Chave no Futuro do Trabalho**

Nossa análise revelou uma clara preferência dos profissionais de dados por modelos de trabalho mais flexíveis. A maioria dos respondentes expressa o desejo de atuar nos modelos Híbrido ou 100% Remoto, com uma baixa preferência pelo trabalho integralmente presencial.

Essa busca por flexibilidade está diretamente ligada à satisfação profissional. Os dados indicam que profissionais com maior flexibilidade em seus modelos de trabalho tendem a apresentar níveis mais altos de satisfação.

Um ponto crucial identificado é o risco de retenção de talentos. Uma parcela significativa dos profissionais que atualmente trabalham de forma remota ou híbrida considera buscar novas oportunidades caso suas empresas exijam um retorno obrigatório ao modelo 100% presencial. Este é um sinal de alerta importante para as organizações.

As preferências detalhadas mostram que a transição para modelos mais flexíveis é um desejo presente em todos os grupos, inclusive entre aqueles que hoje atuam presencialmente.

Em resumo, a flexibilidade no trabalho se consolidou como um fator determinante para a atração e retenção de profissionais de dados. Empresas que conseguirem alinhar suas políticas de trabalho com essa expectativa não apenas aumentarão a satisfação de suas equipes, mas também fortalecerão sua posição no mercado de talentos. Adaptar-se a essa realidade é fundamental para o sucesso no cenário atual e futuro do trabalho.
