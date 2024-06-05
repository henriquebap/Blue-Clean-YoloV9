# Projeto de Detecção de Lixo no Mar usando YOLOv9

## Descrição

Este projeto utiliza o modelo YOLOv9 para a detecção de lixo em imagens de praias e corpos d'água. O objetivo é criar um modelo eficaz que possa identificar e classificar diferentes tipos de resíduos, ajudando em iniciativas de limpeza e preservação ambiental.

## Estrutura do Projeto

- **train_yolov9_object_detection_on_custom_dataset.ipynb**: Notebook contendo o código para treinamento, inferência e anotação usando o modelo YOLOv9.
- **dataset**: Diretório para armazenamento do dataset baixado do Roboflow.

---

## Configuração do Ambiente

1. Clone o repositório:
   ```sh
   git clone https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git

2. Obtenha uma chave de API do Roboflow e configure-a como uma variável de ambiente:
- ´export ROBOFLOW_API_KEY='SUA_CHAVE_DE_API'´

3. Baixe os pesos pré-treinados do modelo:
- ´curl -L "https://github.com/skalskip/yolov9/releases/download/v1.0/yolov9s.pt" -o yolov9s.pt´

---

## Uso
- Abra o notebook train_yolov9_object_detection_on_custom_dataset.ipynb em um ambiente Jupyter.

- Execute todas as células para treinar o modelo, realizar inferências e anotar os resultados.

## Referências
Artigo YOLOv9
Página do Projeto no GitHub
Roboflow
