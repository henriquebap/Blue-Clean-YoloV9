# Blue Clean - Sea Garbage Detection
---
## Projeto de Detecção de Lixo no Mar usando YOLOv9
---
## Tabela de Conteúdos
- [Descrição](#descrição)
- [Objetivo](#objetivo)
- [Configuração do Ambiente](#configuração-do-ambiente)
- [Uso](#uso)
- [Resultados e Análises](#resultados-e-análises)
  - [Treinamento do Modelo](#treinamento-do-modelo)
  - [Validação do Modelo](#validação-do-modelo)
  - [Exemplos de Resultados](#exemplos-de-resultados)
- [Referências](#referências)
- [Equipe](#equipe)

---
## Descrição

Este projeto utiliza a versão mais recente do modelo YOLO, o YOLOv9, para a detecção de lixo em imagens de praias e corpos d'água. O objetivo é criar um modelo eficiente que possa identificar e classificar diferentes tipos de resíduos, contribuindo para iniciativas de limpeza e preservação ambiental.

---

## Objetivo
A Blue Clean é uma iniciativa dedicada a promover a limpeza, organização e eficiência na conservação de nossos mares, oceanos e praias. Desenvolvemos uma solução inovadora que integra geolocalização via Maps e uma Inteligência Artificial baseada em redes neurais convolucionais. Esta IA é capaz de reconhecer e classificar automaticamente resíduos como garrafas plásticas, garrafas de vidro, máscaras e luvas, tanto na superfície quanto no fundo do mar. Nosso compromisso é assegurar que nossas praias e oceanos estejam mais limpos, promovendo um ambiente mais saudável e tecnológicamente avançado para as futuras gerações.

---

## Configuração do Ambiente

1. Clone o repositório:
   ```sh
   git clone https://github.com/https://github.com/henriquebap/Blue-Clean-YoloV9.git

2. Obtenha uma chave de API do Roboflow e configure-a como uma variável de ambiente:
- ´export ROBOFLOW_API_KEY='SUA_CHAVE_DE_API'´

3. Baixe os pesos pré-treinados do modelo:
- ´curl -L "https://github.com/skalskip/yolov9/releases/download/v1.0/yolov9s.pt" -o yolov9s.pt´

---

## Uso
- Abra o notebook YoloV9-ObjectDetection-SeaGarbage.ipynb em um ambiente.

- Execute todas as células para treinar o modelo, realizar inferências e anotar os resultados.

## Resultados e Análises
### Treinamento do Modelo
Após 25 'Epochs', o modelo Apresenta as seguintes metricas:

```
25 epochs completed in 1.048 hours. 
Optimizer stripped from runs/train/exp/weights/last.pt, saved as runs/train/exp/weights/last_striped.pt, 51.5MB 
Optimizer stripped from runs/train/exp/weights/best.pt, saved as runs/train/exp/weights/best_striped.pt, 51.5MB 

Validating runs/train/exp/weights/best.pt... 
Fusing layers... gelan-c summary: 467 layers, 25414044 parameters, 0 gradients, 102.5 GFLOPs 
Class Images Instances P R mAP50 mAP50-95: 100% 16/16 [00:16<00:00, 1.06s/it] 
all 512 1300 0.881 0.88 0.915 0.686 
Mask 512 352 0.907 0.923 0.942 0.75 
gbottle 512 305 0.874 0.839 0.897 0.657 
glove 512 301 0.923 0.955 0.961 0.787 
pbottle 512 342 0.821 0.803 0.859 0.549 
Results saved to runs/train/exp
```

![yoloV9-Results](https://github.com/henriquebap/Blue-Clean-YoloV9/blob/main/images/yoloV9-Results.png)
Metrics Curve

### Validação do Modelo
Na validação, o modelo foi avaliado com as seguintes métricas:

```
val: data=/content/yolov9/Garbage---Sea---Detection-1/data.yaml, weights=['/content/yolov9/runs/train/exp/weights/best.pt'], batch_size=32, imgsz=640, conf_thres=0.001, iou_thres=0.7, max_det=300, task=val, device=0, workers=8, single_cls=False, augment=False, verbose=False, save_txt=False, save_hybrid=False, save_conf=False, save_json=False, project=runs/val, name=exp, exist_ok=False, half=False, dnn=False, min_items=0 YOLOv5 🚀 1e33dbb Python-3.10.12 torch-2.3.0+cu121 CUDA:0 (Tesla T4, 15102MiB) Fusing layers... gelan-c summary: 467 layers, 25414044 parameters, 0 gradients, 102.5 GFLOPs 

val: Scanning /content/yolov9/Garbage---Sea---Detection-1/valid/labels.cache... 
512 images, 0 backgrounds, 0 corrupt: 100% 512/512 [00:00<?, ?it/s] 
Class Images Instances P R mAP50 mAP50-95: 100% 16/16 [00:24<00:00, 1.51s/it] 
all 512 1300 0.88 0.88 0.915 0.685 
Mask 512 352 0.903 0.923 0.943 0.75 
gbottle 512 305 0.874 0.839 0.897 0.655 
glove 512 301 0.923 0.955 0.961 0.787 
pbottle 512 342 0.821 0.804 0.859 0.55 
Speed: 1.2ms pre-process, 30.9ms inference, 4.2ms NMS per image at shape (32, 3, 640, 640) 
Results saved to runs/val/exp
```
![matrixConfusion-YoloV9](https://github.com/henriquebap/Blue-Clean-YoloV9/blob/main/images/matrixConfusion-YoloV9.png)
Confusion Matrix

### Exemplos de Resultados
![glove](https://github.com/henriquebap/Blue-Clean-YoloV9/blob/main/images/glove.jpg)
![test-glove-mask](https://github.com/henriquebap/Blue-Clean-YoloV9/blob/main/images/test-glove-mask.jpg)


## Referências
[![Roboflow](https://raw.githubusercontent.com/roboflow-ai/notebooks/main/assets/badges/roboflow-blogpost.svg)](https://app.roboflow.com/global-solution-sea-garbage/garbage-sea-detection/1) - RoboFlow Workspace

[![GitHub](https://badges.aleen42.com/src/github.svg)](https://github.com/WongKinYiu/yolov9) - YoloV9 Repository

[![arXiv](https://img.shields.io/badge/arXiv-2402.13616-b31b1b.svg)](https://arxiv.org/pdf/2402.13616.pdf) - Artigo do YoloV9

[![GitHub - Henriquebap](https://badges.aleen42.com/src/github.svg)](https://github.com/henriquebap/Blue-Clean-YoloV9/tree/main) - Project Repo

---

Este projeto é parte de um esforço contínuo da Blue Clean para utilizar tecnologia de ponta na preservação ambiental, especificamente na limpeza e monitoramento de áreas marinhas. Agradecemos a todos os colaboradores e convidamos a comunidade a contribuir para melhorar ainda mais esta solução.

---
### Global Solution Group
- [Henrique Baptista](https://www.linkedin.com/in/henrique-baptista777/) - RM97796 (Modelo Criado e Desenvolvido)
- Kaique Oliveira - RM550815
- Rafael Minoro - RM99988
- Thiago Gil - RM551211
- Vitor Pereira - RM551831
