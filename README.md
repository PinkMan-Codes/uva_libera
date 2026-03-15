# uva_libera
Projeto de Machine Learning (K-Means) para segmentação físico-química de vinhos, focado na identificação de um perfil estratégico para o mercado de jovens adultos.

# 🍷 Uva Libera: Segmentação de Portefólio de Vinhos com Machine Learning

## 📌 Visão Geral do Projeto
O presente estudo formaliza-se através de uma abordagem analítica que procura transformar dados químicos brutos em inteligência de negócio acionável. Através do algoritmo de Machine Learning **K-Means**, apoiado por métricas estatísticas de validação (Regra do Cotovelo e Coeficiente *Silhouette*), explorou-se a divisão ideal do portefólio de vinhos.

A matemática sugeria inicialmente quatro *clusters*, mas o modelo foi estrategicamente recalibrado para três, evitando nichos demasiado pequenos e garantindo segmentos com verdadeira utilidade comercial para o mercado.

## 🎯 Impacto de Negócio
A análise confirmou a existência de um segmento-alvo perfeitamente alinhado com a estratégia da Uva Libera. Este *cluster* destaca-se pela **elevada frescura** (ácido cítrico), **doçura percetível** (açúcar residual) e **baixo teor alcoólico** — o perfil ideal para atrair a nova geração de jovens adultos.

---

## 📊 O Dataset
Os dados utilizados neste projeto consistem num ficheiro `.csv` contendo as características físico-químicas de várias amostras de vinho. 
* **Variáveis iniciais:** Incluíam propriedades como *fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates* e *alcohol*.
* **Objetivo dos dados:** O *dataset* não possui rótulos de "qualidade" ou "tipo de cliente". É um problema clássico de **Aprendizagem Não Supervisionada** (*Unsupervised Learning*), onde o objetivo é deixar o algoritmo descobrir padrões ocultos na química dos vinhos.

---

## 🧠 Fases do Projeto (Como a Magia Acontece)

### Fase 1: Análise Exploratória e Limpeza (EDA)
Antes de modelar, é preciso conhecer os dados. Calculámos o **Coeficiente de Variação** para perceber a dispersão de cada variável química e garantir que não havia erros graves.

### Fase 2: Combate à Multicolinearidade (Correlações)
Algoritmos como o K-Means são sensíveis a informações repetidas. Analisámos a matriz de correlação par-a-par para detetar variáveis que diziam o mesmo ao modelo. Decidimos **excluir variáveis redundantes** (como *pH* e *sulphur dioxide*) para criar um modelo robusto e sem enviesamentos.

### Fase 3: Modelação com K-Means e Padronização
1. **Padronização (`StandardScaler`):** Como variáveis como "Densidade" (valores muito pequenos) e "Açúcar" (valores maiores) têm escalas diferentes, normalizámos tudo para que o K-Means as tratasse de forma justa, medindo distâncias de forma correta.
2. **Definição do `k`:** Utilizámos a **Regra do Cotovelo** (Inércia) e o **Coeficiente Silhouette** num gráfico de duplo eixo para encontrar a divisão matemática perfeita.

### Fase 4: Perfilamento de Negócio
Com os grupos criados, usámos a função `groupby` para calcular a média química de cada *cluster*. Transformámos estes números no "Bilhete de Identidade" de cada vinho, apresentando os resultados através de **Gráficos de Radar** e **Gráficos 3D** interativos (via *Plotly*) para facilitar a visualização por parte dos gestores.

---

## 🚀 Como Executar este Projeto (Download e Upload)

Se quiseres explorar o código, ver os gráficos 3D interativos ou testar os teus próprios dados, podes fazê-lo facilmente através do **Google Colab** (não precisas de instalar nada no teu computador).

### Passo 1: Fazer o Download dos Ficheiros
1. No topo desta página do GitHub, clica no botão verde **"<> Code"**.
2. Seleciona **"Download ZIP"**.
3. Extrai o ficheiro ZIP no teu computador. Vais encontrar lá dentro o *notebook* (`.ipynb`) e o ficheiro de dados (`.csv`).

### Passo 2: Fazer Upload para o Google Colab
1. Acede ao [Google Colab](https://colab.research.google.com/).
2. Na janela que abre, escolhe o separador **"Upload"** (Carregar).
3. Arrasta o ficheiro `.ipynb` (que descarregaste no Passo 1) para essa janela. O código vai abrir imediatamente.

### Passo 3: Adicionar os Dados e Correr o Código
1. No Google Colab, olha para o menu lateral esquerdo e clica no ícone da **Pasta** (Ficheiros).
2. Clica no ícone de "Upload" (uma folha com uma seta para cima) e carrega o ficheiro `.csv` do *dataset*.
3. Agora é só ires ao menu superior, clicares em **"Runtime" (Ambiente de execução)** e depois em **"Run all" (Executar tudo)**. 
4. Explora os gráficos e as conclusões desenvolvidas ao longo do projeto.
