# 📘 Repositório de Aulas — Machine Learning
**Fatec Jahu · DSM · 5º Semestre**
**Professor: Tiago Silva**

Repositório com todos os notebooks, datasets e exercícios desenvolvidos na disciplina de **Aprendizagem de Máquina**. Os algoritmos foram implementados **do zero**, usando apenas `NumPy`, `Matplotlib` e `CSV` — sem bibliotecas de ML prontas como scikit-learn — para garantir a compreensão profunda de cada conceito.

---

## 🛠️ Tecnologias Utilizadas

| Biblioteca | Finalidade |
|---|---|
| Python 3 | Linguagem principal |
| NumPy | Operações matemáticas e manipulação de arrays/matrizes |
| Matplotlib | Geração de gráficos e visualizações |
| CSV / csv.reader | Leitura de datasets no formato `.csv` |
| Jupyter Notebook | Ambiente de desenvolvimento interativo |

---

## 🗂️ Estrutura do Repositório

```
Machine_Learning/
├── aula01/   → Introdução ao ML e primeiro gráfico
├── aula02/   → Fundamentos de Python e OOP
├── aula03/   → Exercícios de Orientação a Objetos
├── aula04/   → Biblioteca NumPy
├── aula05/   → Visualização com Matplotlib
├── aula06/   → Regressão Linear Simples (do zero)
├── aula07/   → Aplicação em dataset de imóveis (kc_house_data)
├── aula08/   → Regressão Linear Múltipla
├── aula09/   → Regressão Logística (dataset Titanic)
├── aula10/   → Matriz de Confusão e métricas de avaliação
├── aula11/   → KNN — K-Nearest Neighbors (classificação de tumores)
├── aula12/   → Exercícios KNN
├── aula13/   → Exercícios de classificação variada
├── aula14/   → Árvore de Decisão (do zero)
├── aula15/   → Exercícios com Árvore de Decisão
├── aula16/   → Perceptron (rede neural simples)
├── aula17/   → MLP — Multi-Layer Perceptron
├── aula18/   → K-Means (clusterização)
├── aula19/   → Exercícios de revisão (K-Means em múltiplos datasets)
└── aula20/   → Revisão geral — escolha do algoritmo certo por problema
```

---

## 📚 Conteúdo Aula por Aula

---

### 🟢 Aula 01 — Introdução ao Machine Learning

Primeiro contato com o ambiente e com as ferramentas. Instalação das bibliotecas `numpy` e `matplotlib` via `%pip install`. Criação do primeiro gráfico de linha simples com dados de vendas ao longo dos anos.

**Conceitos abordados:** o que é Machine Learning, como funciona o Jupyter Notebook, estrutura de um projeto de dados.

**Arquivo:** `aula1.ipynb`

---

### 🟢 Aula 02 — Fundamentos de Python

Revisão dos conceitos essenciais de Python necessários para o desenvolvimento em ML.

**Tópicos:**
- Variáveis e tipos de dados (`int`, `float`, `str`, `bool`)
- Estruturas de dados: `list` (mutável), `tuple` (imutável), `dict` (chave-valor)
- Estruturas de controle: `if/else`, `for`, list comprehensions
- Funções com parâmetros padrão e funções `lambda` (anônimas)
- Orientação a Objetos: classes, atributos e métodos

**Arquivos:** `Fundamentos.ipynb`, `OOP.ipynb`

---

### 🟢 Aula 03 — Exercícios de Orientação a Objetos

Prática de POO com três exercícios progressivos:

1. **Classe `Aluno`** — armazena nome e lista de notas; calcula média e verifica aprovação (média ≥ 6)
2. **Classe `Conversor`** — atributo privado `__taxa_dolar`; valida taxa negativa; converte Real → Dólar
3. **Classes `Livro` e `Biblioteca`** — composição de objetos; a `Biblioteca` mantém uma lista de `Livro` e permite adicionar e listar títulos

**Conceito importante:** encapsulamento com atributo privado (`__taxa_dolar`) e validação via `raise ValueError`.

**Arquivo:** `aula03.ipynb`

---

### 🟢 Aula 04 — NumPy

Fundamento matemático de todo o curso. O NumPy permite trabalhar com vetores e matrizes de forma eficiente, sem precisar de loops manuais (vetorização).

**Tópicos:**
- Criação de arrays 1D (vetores) e 2D (matrizes) com `np.array()`
- Funções utilitárias: `np.zeros()`, `np.ones()`, `np.arange()`, `np.linspace()`
- Inspeção: `.shape`, `.ndim`, `.size`, `.dtype`
- Operações matemáticas elemento a elemento: `+`, `-`, `*`, `/`
- Estatísticas: `np.mean()`, `np.std()`, `np.max()`
- Indexação e fatiamento (slicing): `arr[1:4]`, `matriz[1, 2]`, `matriz[:, 1]`

**Por que importa para ML:** arrays NumPy são a base de todos os datasets, pesos de redes neurais e cálculos de matrizes que usamos nas aulas seguintes.

**Arquivo:** `numpy.ipynb`

---

### 🟢 Aula 05 — Visualização de Dados com Matplotlib

Ferramenta de apoio visual para entender os dados antes e depois de treinar modelos.

**Tipos de gráficos criados:**
- **Gráfico de linha** (`plt.plot`) — evolução de vendas ao longo do tempo
- **Gráfico de barras** (`plt.bar`) — comparação entre produtos
- **Scatter plot** (`plt.scatter`) — relação entre duas variáveis numéricas (base visual da regressão)

**Personalização:** títulos, rótulos de eixo, grid, legendas.

**Arquivo:** `matplotlib.ipynb`

---

### 🔵 Aula 06 — Regressão Linear Simples (implementação do zero)

Primeiro algoritmo de Machine Learning da disciplina. A regressão linear prevê um valor numérico contínuo com base em uma variável de entrada.

**O que foi implementado:**
- Leitura do `dataset.csv` com `np.loadtxt()`
- Separação em variável independente `X` e variável dependente `y`
- Reshape dos arrays para formato matricial (`reshape(-1, 1)`)
- Cálculo dos coeficientes `a` (intercepto) e `b` (inclinação) com `np.polyfit()`
- Geração das previsões: `y_pred = a + b * X`
- **Coeficiente de Correlação de Pearson (r):** mede a força da relação linear entre X e y
- **Coeficiente de Determinação (R²):** indica quanto da variação de y é explicada por X

**Visualização:** scatter plot dos dados reais + linha de regressão em vermelho.

**Arquivos:** `regressao_linear.ipynb`, `dataset.csv`

---

### 🔵 Aula 07 — Aplicação: Predição de Preços de Imóveis

Aplicação da regressão linear simples em um dataset real com mais de 21 mil registros de imóveis de King County (EUA).

**Relações analisadas (variável alvo: preço do imóvel):**
- Preço × número de quartos (`bedrooms`)
- Preço × número de banheiros (`bathrooms`)
- Preço × número de andares (`floors`)

Para cada combinação: scatter plot dos dados + linha de regressão + valores de `r` e `R²`.

**Arquivos:** `kc_house_data.csv`, `precos_bedroom.ipynb`, `precos_bathroom.ipynb`, `precos_floor.ipynb`, `regress_kc.ipynb`

---

### 🔵 Aula 08 — Regressão Linear Múltipla

Extensão da regressão simples para múltiplas variáveis preditoras, aumentando a precisão do modelo.

**Fórmula matricial dos coeficientes:**
```
β = (XᵀX)⁻¹ Xᵀy
```
Onde:
- `X.T` — transposta da matriz X
- `@` — multiplicação de matrizes em Python
- `np.linalg.inv()` — inversa da matriz

**Aplicação prática:** predição do preço de imóveis usando simultaneamente `bedrooms`, `bathrooms` e `sqft_living` como variáveis preditoras.

**Diferencial da aula:** comparação entre o modelo simples e o múltiplo para mostrar a melhora na precisão.

**Arquivos:** `regressao_multipla.ipynb`, `regressao_multipla_menor_diferenca.ipynb`, `kc_house_data.csv`

---

### 🔵 Aula 09 — Regressão Logística

Transição do problema de **regressão** (prever número) para **classificação** (prever categoria). Dataset: sobreviventes do Titanic.

**Implementação do zero:**

| Etapa | O que faz |
|---|---|
| `load_data()` | Lê o CSV e converte features: sexo → 0/1, valores ausentes → -1 |
| `fill_missing_age()` | Preenche idades faltantes com a média |
| `normalize()` | Normalização: `(X - média) / desvio padrão` |
| `add_bias()` | Adiciona coluna de 1s para o termo de intercepto |
| `sigmoid(z)` | Converte qualquer número em probabilidade: `1 / (1 + e⁻ᶻ)` |
| `compute_cost()` | Calcula a perda (log loss) |
| `gradient_descent()` | Atualiza os pesos iterativamente para minimizar o erro |

**Features usadas:** `pclass`, `sex`, `age`, `sibsp`, `parch`, `fare`

**Arquivos:** `regressao_logistica.ipynb`, `titanic.csv`

---

### 🔵 Aula 10 — Matriz de Confusão e Métricas de Avaliação

Continuação da aula 09, com foco em **como medir a qualidade** do modelo de classificação.

**Métricas implementadas:**

| Métrica | O que mede |
|---|---|
| **Acurácia** | % de previsões corretas no total |
| **Precisão** | Das previsões positivas, quantas estão corretas |
| **Recall (Sensibilidade)** | Dos casos positivos reais, quantos foram detectados |
| **F1-Score** | Média harmônica entre precisão e recall |

**Matriz de Confusão:**
```
                 Previsto Positivo  Previsto Negativo
Real Positivo  |  Verdadeiro Pos.  |  Falso Negativo  |
Real Negativo  |  Falso Positivo   |  Verdadeiro Neg. |
```

**Arquivos:** `regressao_logistica_matriz_confusao.ipynb`, `titanic.csv`

---

### 🟠 Aula 11 — KNN — K-Nearest Neighbors

Algoritmo de classificação baseado em proximidade: um novo ponto recebe a classe mais comum entre seus `k` vizinhos mais próximos.

**Dataset:** tumores (tamanho em cm × textura) → classificar como Benigno (0) ou Maligno (1)

**Implementação do zero:**

```python
def calcular_distancia_euclidiana(ponto1, ponto2):
    return np.sqrt(np.sum((ponto1 - ponto2) ** 2))

def encontrar_vizinhos(X_train, y_train, ponto_teste, k):
    # Calcula distância para todos os pontos de treino
    # Ordena e retorna os k mais próximos

def prever_classificacao(vizinhos):
    # Voto majoritário: a classe mais frequente vence
```

**Visualização:** scatter plot separando tumores benignos (azul) e malignos (vermelho).

**Arquivos:** `KNN_analise.ipynb`, `tumores.csv`

---

### 🟠 Aula 12 — Exercícios de KNN

Três exercícios aplicando KNN em datasets diferentes, variando o valor de `k` e as features de entrada para observar o impacto na classificação.

**Arquivos:** `exercicio1.ipynb`, `exercicio2.ipynb`, `exercicio3.ipynb` + respectivos CSVs

---

### 🟠 Aula 13 — Exercícios de Classificação

Exercícios práticos que consolidam os algoritmos de classificação vistos até o momento, aplicados a novos datasets com diferentes características.

**Foco:** tratamento de dados, treinamento, predição e análise dos resultados.

**Arquivos:** `exercicio1.ipynb`, `exercicio2.ipynb`, `exercicio3.ipynb` + datasets correspondentes

---

### 🟠 Aula 14 — Árvore de Decisão (implementação do zero)

Algoritmo que aprende a classificar dados fazendo perguntas binárias (ex: "a idade é ≤ 40?") e construindo uma estrutura em árvore.

**Implementação do zero:**

| Componente | Descrição |
|---|---|
| `entropia(y)` | Mede a "impureza" de um conjunto: `−Σ p·log₂(p)` |
| `dividir()` | Separa os dados em dois grupos com base em um limiar |
| `class No` | Nó da árvore: guarda qual feature usar, o limiar de corte e os filhos |
| `class ArvoreDecisao` | Constrói a árvore recursivamente com `_crescer()` |
| `ajustar(X, y)` | Treina a árvore nos dados |
| `prever(X)` | Percorre a árvore para classificar novos pontos |

**Condições de parada:** profundidade máxima atingida, número mínimo de amostras ou classe pura (entropia = 0).

**Dataset:** idade × salário → aprovação de crédito (0 ou 1)

**Arquivos:** `arvore_decisao.ipynb`, `dataset.csv`

---

### 🟠 Aula 15 — Exercícios com Árvore de Decisão

Três exercícios aplicando a Árvore de Decisão em cenários variados:

- **Exercício 1:** previsão com base em idade, experiência e quantidade de treinamentos
- **Exercício 2:** análise com renda, idade e score de crédito
- **Exercício 3:** previsão de suporte com base em meses de contrato e valor pago

Cada exercício possui múltiplas combinações de features testadas separadamente.

**Arquivos:** 9 notebooks + 3 datasets CSV

---

### 🔴 Aula 16 — Perceptron

Introdução às **Redes Neurais Artificiais**. O Perceptron é o neurônio artificial mais simples: recebe entradas, multiplica pelos pesos, soma e passa por uma função de ativação (degrau).

**Implementação da classe `Perceptron`:**

| Método | Função |
|---|---|
| `_initialize_weights()` | Inicializa pesos: `random`, `zeros` ou `normal` |
| `fit(X, y)` | Treina: para cada erro, ajusta pesos com `w += lr × erro × x` |
| `predict(X)` | Classifica: retorna 1 se `w·x + bias ≥ 0`, senão 0 |
| `plot_decision_boundary()` | Desenha a fronteira de separação aprendida |
| `plot_comparison()` | Compara dataset original × fronteira de decisão |

**Parâmetros ajustáveis:** `learning_rate`, `n_epochs`, `weight_init`

**Limitação importante:** o Perceptron só funciona em dados **linearmente separáveis**. Quando os dados não podem ser separados por uma linha reta, ele falha — o que motiva o MLP.

**Datasets:** 3 pares treino/teste (dataset1, 2 e 3) para comparar dados separáveis e não separáveis.

**Arquivo:** `perceptron.ipynb`

---

### 🔴 Aula 17 — MLP — Multi-Layer Perceptron

Evolução do Perceptron: rede neural com **múltiplas camadas** (entrada → camadas ocultas → saída), capaz de aprender padrões não-lineares.

**Diferenças em relação ao Perceptron simples:**

| Característica | Perceptron | MLP |
|---|---|---|
| Camadas | 1 (só saída) | Múltiplas (ocultas + saída) |
| Padrões aprendidos | Lineares | Não-lineares |
| Função de ativação | Degrau | Sigmoid / ReLU |
| Treinamento | Regra do Perceptron | Backpropagation |

**Datasets:** 3 conjuntos de treino, teste e validação. O conjunto de **validação** é um conceito novo nesta aula — serve para monitorar o desempenho durante o treino sem usar os dados de teste.

**Arquivos:** `MLP.ipynb` + datasets de treino, teste e validação

---

### 🟣 Aula 18 — K-Means (Clusterização)

Primeiro algoritmo de **aprendizado não supervisionado** da disciplina. Ao contrário dos anteriores, não há rótulos — o algoritmo descobre sozinho os grupos nos dados.

**Implementação do zero:**

```python
def kmeans(X, k=3, max_iter=100):
    # 1. Escolhe k pontos aleatórios como centróides iniciais
    # 2. Associação: cada ponto recebe o centróide mais próximo
    # 3. Atualização: novo centróide = média dos pontos do cluster
    # 4. Repete até os centróides não mudarem (convergência)
```

**Dataset:** clientes segmentados por frequência de compras/mês × ticket médio (R$)

**Visualização:** scatter plot com cores por cluster + marcadores "X" nos centróides.

**Aplicação:** segmentação de clientes para estratégias de marketing personalizadas.

**Arquivos:** `kmeans.ipynb`, `dataset_clientes_kmeans.csv`

---

### 🟣 Aula 19 — Revisão P2: Exercícios de K-Means

Aplicação do K-Means em quatro datasets diferentes para consolidar o aprendizado antes da prova.

| Exercício | Dataset | Segmentação por |
|---|---|---|
| 1 | `dataset_marketing.csv` | Renda anual × score de gastos |
| 2 | `dataset_credito.csv` | Variáveis de crédito |
| 3 | `dataset_fraude.csv` | Detecção de padrões suspeitos |
| 4 | `dataset_investimentos.csv` | Perfil de investidores |

**Arquivos:** `exercicio1.ipynb` a `exercicio4.ipynb` + respectivos datasets

---

### 🟣 Aula 20 — Revisão Geral: Escolhendo o Algoritmo Certo

Revisão completa da disciplina com foco em **saber qual algoritmo aplicar** para cada tipo de problema.

**Questões da revisão:**

| Questão | Dataset | Algoritmo escolhido | Justificativa |
|---|---|---|---|
| 1 | Marketing (renda × score) | **K-Means** | Sem rótulos → aprendizado não supervisionado |
| 2 | Crédito | **Regressão Logística ou Árvore** | Com rótulos → classificação supervisionada |
| 3 | Fraude | **KNN ou Árvore de Decisão** | Classificação binária com padrões locais |
| 4 | Investimentos | **K-Means** | Segmentação sem rótulos definidos |

**Pasta:** `Revisao_MaquinaDeAprendizagem/Questao1` a `Questao4`

---

## 🎯 Objetivo da Disciplina

Compreender os fundamentos dos principais algoritmos de Machine Learning implementando-os do zero com Python puro, NumPy e Matplotlib — sem depender de bibliotecas de alto nível — para desenvolver raciocínio matemático e lógico aplicado à ciência de dados.

---

## 👩‍💻 Desenvolvido por

**Amanda Frolini** — Fatec Jahu, DSM 5º Semestre
