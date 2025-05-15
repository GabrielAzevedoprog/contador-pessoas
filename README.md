# Contador de Pessoas na Escada Rolante

Este projeto utiliza **visão computacional com OpenCV** para contar o número de pessoas que passam por uma escada rolante em um vídeo.

## 📹 Descrição

O script processa um vídeo (`escalator.mp4`) em tempo real, detectando movimentações em uma região específica da imagem. Quando o número de pixels brancos (indicando movimento) nessa região ultrapassa um certo limite, o contador de pessoas é incrementado. O sistema também possui uma lógica de "liberação" para evitar múltiplas contagens da mesma pessoa.

---

## ⚙️ Requisitos

* Python 3.x
* OpenCV (`cv2`)
* NumPy

Você pode instalar os requisitos com:

```bash
pip install opencv-python numpy
```

---

## 🚀 Como Usar

1. Coloque o vídeo `escalator.mp4` na mesma pasta do script.
2. Execute o script Python:

```bash
python contador_escada.py
```

3. A janela exibirá:

   * O vídeo original com contorno visual da área de contagem.
   * Um número representando a quantidade de pessoas detectadas.
   * A contagem de pixels na região analisada.

---

## 🧠 Lógica do Funcionamento

* A imagem é convertida para escala de cinza e binarizada.
* Uma região de interesse (ROI) é definida para detectar passagem.
* Quando há mais de 4000 pixels brancos no ROI, e o sistema está "liberado", a contagem é incrementada.
* A flag `liberado` evita que uma mesma pessoa seja contada várias vezes em frames consecutivos.

---

## 🖼️ Interface Visual

* **Retângulo Verde**: Indica que o sistema está pronto para detectar uma nova pessoa.
* **Retângulo Magenta**: Uma pessoa foi detectada e contada.
* **Contador Azul**: Número total de pessoas detectadas.

---

## 📁 Estrutura

```
.
├── escalator.mp4
├── contador_escada.py
└── README.md
```

---

## 📌 Observações

* O valor de `4000` pixels pode precisar ser ajustado dependendo da iluminação, ângulo da câmera ou resolução do vídeo.
* O sistema é simples e não utiliza detecção por IA, apenas processamento de imagem tradicional.

---
