[README.md](https://github.com/user-attachments/files/32473919/README.md)
# 💊 Pill Image Classification
### Классификация таблеток по изображениям

[English](#english) · [Русский](#русский)

---

<a id="english"></a>

## 🇬🇧 English

### Overview

A computer vision project for multiclass classification of pill images using transfer learning.

The model receives an image of a pill and predicts its class. A pretrained **MobileNetV3-small** is used as the backbone. The project first trains a new classifier with the pretrained feature extractor frozen, then fine-tunes the final feature block with a smaller learning rate.

###  Result

**Validation accuracy: 77.78%**

Training only the new classifier produced an accuracy of **69.44%**. After fine-tuning the final feature block, accuracy increased to **77.78%**.

###  Model

- MobileNetV3-small pretrained on ImageNet
- custom classification layer
- transfer learning
- fine-tuning of the final feature block
- CrossEntropyLoss
- Adam optimizer

###  Image preprocessing

Images are resized to `224 × 224` and normalized using ImageNet statistics. Training augmentation includes horizontal and vertical flips and small random rotations.

###  Error analysis

The notebook includes per-class error analysis, identifies the five classes with the largest number of mistakes, and checks which classes are recognized without errors.

Possible error sources include visual similarity between different pill classes, lighting differences and camera angle.

### Data

The dataset is **not included** in this public repository. To reproduce the notebook, place the data locally in a `dataset/` directory with separate training and validation folders.

---

<a id="русский"></a>

## 🇷🇺 Русский

### О проекте

Проект посвящён многоклассовой классификации изображений таблеток с помощью компьютерного зрения и transfer learning.

Модель получает фотографию таблетки и предсказывает её класс. В качестве основы используется предобученная **MobileNetV3-small**. Сначала обучается новый классификатор при замороженной предобученной части сети, после чего выполняется fine-tuning последнего блока признаков с меньшим learning rate.

###  Результат

**Accuracy на валидационной выборке: 77.78%**

При первоначальном обучении только нового классификатора accuracy составила **69.44%**. После fine-tuning последнего блока признаков результат вырос до **77.78%**.

###  Модель

- MobileNetV3-small с предобученными весами ImageNet
- новый классификационный слой
- transfer learning
- fine-tuning последнего блока признаков
- CrossEntropyLoss
- Adam

### Предобработка изображений

Изображения приводятся к размеру `224 × 224` и нормализуются статистиками ImageNet. Для обучающей выборки используются аугментации: горизонтальные и вертикальные отражения и небольшие случайные повороты.

###  Анализ ошибок

В ноутбуке проведён анализ ошибок по классам, определены пять классов с наибольшим количеством ошибок и классы, распознанные без ошибок.

Возможными причинами ошибок являются визуальное сходство таблеток разных классов, различия в освещении и ракурсе съёмки.

###  Данные

Датасет **не публикуется** в этом репозитории. Для воспроизведения ноутбука данные необходимо разместить локально в директории `dataset/`, разделив их на обучающую и валидационную части.

---

##  Tech Stack

`Python` · `PyTorch` · `torchvision` · `MobileNetV3` · `scikit-learn` · `NumPy` · `Matplotlib`

##  Repository Structure

```text
pill-image-classification/
├── notebook.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

##  Installation

```bash
pip install -r requirements.txt
```

The complete training process, evaluation metrics and error analysis are available in `notebook.ipynb`.

Полный процесс обучения, метрики качества и анализ ошибок находятся в `notebook.ipynb`.
