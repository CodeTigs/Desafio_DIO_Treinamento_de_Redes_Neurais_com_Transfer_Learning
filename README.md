# Projeto de Transfer Learning: Classificador de Gatos vs Cachorros 🐱🐶

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)]()
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)]()
[![Google Colab](https://img.shields.io/badge/Colab-F9AB00?style=flat&logo=googlecolab&color=525252)]()

## 📌 Sobre o Projeto
Este repositório contém a implementação de um projeto prático de **Deep Learning** focado na aplicação da técnica de **Transfer Learning**. O objetivo é classificar imagens entre duas classes (Gatos e Cachorros) utilizando uma rede neural pré-treinada, otimizando o tempo de processamento e alcançando alta precisão computacional.

Projeto desenvolvido como parte dos desafios de projeto da **DIO**.

## 🛠️ Tecnologias e Ferramentas
* **Linguagem:** Python
* **Framework:** TensorFlow / Keras
* **Ambiente de Desenvolvimento:** Google Colab
* **Bibliotecas auxiliares:** `tensorflow_datasets` (para extração dos dados), `matplotlib` (para visualização dos gráficos de desempenho).

## 🧠 Arquitetura e Modelo
Foi utilizada a arquitetura **MobileNetV2**, desenvolvida pelo Google. 
* **Por que a MobileNetV2?** É uma rede extremamente leve e eficiente, ideal para dispositivos móveis e ambientes com recursos limitados, sem perder a capacidade de extração de características (features).
* **Transfer Learning:** O modelo base foi pré-treinado no dataset *ImageNet* (que contém milhões de imagens). Congelamos os pesos das camadas convolucionais (base) e substituímos o "topo" da rede por uma nova camada densa (`Dense`) configurada para classificação binária (Gato = 0, Cachorro = 1).

## 📊 Estrutura do Pipeline
1. **Aquisição de Dados:** Download do dataset `cats_vs_dogs` direto via `tensorflow_datasets`.
2. **Pré-processamento:** * Limpeza de imagens corrompidas (tratado automaticamente pelo tfds).
   * Redimensionamento de todas as imagens para `160x160` pixels.
   * Divisão em lotes (`batches`) para otimização de memória RAM no Colab.
3. **Modelagem:** Carregamento da base da MobileNetV2, aplicação de `GlobalAveragePooling2D` e `Dropout` (para evitar *overfitting*).
4. **Treinamento e Avaliação:** Treinamento das novas camadas e geração de gráficos de *Acurácia* e *Loss* (Erro).

## 🚀 Como Executar
1. Clone este repositório.
2. Abra o arquivo `.ipynb` no [Google Colab](https://colab.research.google.com/).
3. Vá em `Ambiente de execução` > `Executar tudo` (ou rode célula por célula).
4. Não é necessário fazer o download manual de nenhum dataset, o código já resolve isso automaticamente na primeira célula.

---
