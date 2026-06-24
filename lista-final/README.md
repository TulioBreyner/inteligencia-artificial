# Lista Final - Classificação de Cogumelos (Combined Kaggle Mushrooms)

Este projeto realiza a classificação multiclasse de imagens de cogumelos a partir do dataset *Combined Kaggle Mushrooms*. Para reduzir o tempo, a amostra contém as **5 espécies mais comuns** do dataset, com **1.000 imagens por classe** (5.000 imagens no total).

## Estrutura do Repositório

- `lista-final.ipynb`: Notebook Jupyter contendo todo o fluxo do projeto:
  1. Carregamento e filtragem das imagens via biblioteca `kagglehub`.
  2. Análise Exploratória (EDA): distribuição de classes e amostragem visual.
  3. Pré-processamento: Resize (128x128), normalização (ImageNet) e aumentação de dados.
  4. Definição do Modelo 1 (CNN do Zero) e Modelo 2 (ResNet18 via Transfer Learning).
  5. Treinamento de ambos os modelos por 5 épocas com otimizador Adam e perda por Cross-Entropy.
  6. Avaliação de acurácia, F1-score e plots das matrizes de confusão.
- `requirements.txt`: Arquivo listando as dependências do Python.
- `RELATORIO.md`: Relatório técnico detalhando a metodologia, escolhas de pré-processamento, resultados e discussões sobre os erros e limitações.
- `graficos/`: Pasta com os gráficos gerados pelo notebook (EDA, curvas de aprendizado e matriz de confusão).
- `resultados/`: Pasta com as métricas exportadas e pesos salvos dos modelos (`.pth`).

## Como Executar Localmente

### 1. Requisitos do Sistema
Para utilizar a aceleração por GPU, é necessário possuir drivers NVIDIA instalados no sistema.

### 2. Configurar o Ambiente Virtual
Na raiz do workspace, crie e ative um ambiente virtual do Python:

```powershell
# Criar ambiente virtual
python -m venv venv

# Ativar no Windows (PowerShell)
.\venv\Scripts\Activate.ps1
```

### 3. Instalar Dependências
```powershell
pip install torch torchvision --index-url https://download.pytorch.org/whl/cu130
pip install pandas numpy matplotlib seaborn scikit-learn pillow tqdm jupyter
```

*(Ou o arquivo `requirements.txt`).*

### 4. Executar o Notebook

```powershell
jupyter notebook lista-final/lista-final.ipynb
```

## Principais Resultados

| Modelo | Acurácia Global | F1-Score (Macro) | F1-Score (Weighted) |
|---|---:|---:|---:|
| CNN do Zero | 71,60% | 71,42% | 71,42% |
| **ResNet18 (Transfer Learning)** | **84,00%** | **84,18%** | **84,18%** |

O uso de **Transfer Learning** (com os pesos congelados da ResNet18 pré-treinada no ImageNet) resultou em um ganho de **+12,40%** na acurácia global, superando a CNN básica inicializada do zero.
