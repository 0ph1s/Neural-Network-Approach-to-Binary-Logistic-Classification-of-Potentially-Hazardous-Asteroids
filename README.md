# 🌌 Classificação de Asteroides com Redes Neurais

Este projeto utiliza **Redes Neurais Artificiais** para classificar asteroides como **perigosos** ou **não perigosos** com base em dados astronômicos. A rede é treinada utilizando **regressão logística binária**, **gradiente descendente** e ajuste automático de hiperparâmetros com **KerasTuner**.

## 📊 Dataset

Os dados são provenientes do Kaggle:  
🔗 [NASA Nearest Earth Objects](https://www.kaggle.com/datasets/sameepvani/nasa-nearest-earth-objects?resource=download)

A variável-alvo é `hazardous`, indicando se o asteroide representa risco para a Terra (`1` para perigoso, `0` para não perigoso).

### 📥 Atributos utilizados:
- `est_diameter_min` e `est_diameter_max`: Diâmetros estimados.
- `relative_velocity`: Velocidade relativa.
- `miss_distance`: Distância mínima de aproximação.
- `absolute_magnitude`: Brilho absoluto.

## 🧠 Arquitetura da Rede Neural

- Camadas ocultas densamente conectadas com **ReLU**
- Camada de saída com ativação **sigmoid** (probabilidade entre 0 e 1)
- Otimizador: **Adam**
- Função de perda: **Binary Crossentropy**

O número de camadas, neurônios e taxa de aprendizado são ajustados automaticamente via busca aleatória (`RandomSearch` com `KerasTuner`).

## ⚙️ Ajuste de Hiperparâmetros

Com `KerasTuner` foram testados:
- Número de camadas ocultas: 1 a 3
- Neurônios por camada: 8 a 64
- Taxa de aprendizado (η): entre 0.0001 e 0.01 (log scale)

## 🧪 Resultados

- **Acurácia final**: 91%
- **AUC (Área sob a Curva ROC)**: 0.91

### 🎯 Métricas de Classificação:
| Classe       | Precisão | Revocação |
|--------------|----------|-----------|
| Não Perigoso | 0.92     | 0.99      |
| Perigoso     | 0.73     | 0.14      |

### 🔢 Matriz de Confusão
```
[[16346    93]
 [ 1480   249]]
```

## 📈 Visualizações

- **Curva ROC**  
- **Acurácia por época (treinamento e validação)**  
- **Perda por época (treinamento e validação)**  

## 📚 Fundamentos Matemáticos

Este projeto está embasado em uma análise matemática completa:

- **Função de perda**:  
  \( L(y, \hat{y}) = -[y \log(\hat{y}) + (1 - y)\log(1 - \hat{y})] \)

- **Atualização dos pesos com gradiente descendente**:  
  \( ec{w}_{t+1} = ec{w}_t - \eta \cdot 
abla L(ec{w}_t) \)

- Condições de ótimo:  
  - Gradiente nulo  
  - Hessiana positiva definida

Veja o PDF completo com a análise matemática: [`Neural_Network-3.pdf`](Neural_Network-3.pdf)

## 📁 Estrutura do Projeto

```
📦 asteroid-classification
├── 📄 neo.csv               # Dataset original
├── 📄 modelo_neural.py      # Código do projeto
├── 📄 Neural_Network-3.pdf  # Análise matemática
├── 📄 README.md             # Este arquivo
```

## 🚀 Como Executar

1. Instale as dependências:
```bash
pip install pandas numpy matplotlib scikit-learn tensorflow keras-tuner
```

2. Execute o código:
```bash
python modelo_neural.py
```

---

## ✍️ Autor

Peterson Carara Junior  
📅 Junho, 2025

---