# Aug-MSSD: Small Object Detection

This course project is for 2019 Fall Artificial Intelligence in Shanghai Jiao Tong University. 

I work with [Xiaocheng](https://github.com/currybur), and [Yichen](https://github.com/HesperX), they make great contributions to our project.

Our topic is small object detection, and the main contributions are shown as follows: 

- **Based on SSD, design Aug-MSSD, a multi-feature fusion network with data augmentation.**

- Combine multi-scale features extracted from different layers and customized Data Augmentation methods, including instance-level and image-level transformation of small objects to make the precision higher.

- Achieve **7 mAP improvement** in XS and Small objects over SSD, and **finally win an excellent evaluation**.

---

### Background

Recent great progress on object detection is stimulated by the deep learning pipelines, such as Faster R-CNN, Yolo and SSD. These pipelines indeed work well on large object with high resolution, clear appearance and structure from which the discriminative features can be learned. However, they usually fail to detect very small objects, as rich representations are difficult to learn from their poor-quality appearance and structure. Moreover, two stage detectors such as Faster R-CNN are more likely to perform better than one stage detectors, e.g., Yolo and SSD. In this project, you are required to improve detection performance on small objects based on the SSD pipeline.

### Datasets

****

**Download VOC2007 trainval & test**

```sh
# specify a directory for dataset to be downloaded into, else default is ~/data/
sh data/scripts/VOC2007.sh # <directory>
```

**Download VOC2012 trainval**

```sh
# specify a directory for dataset to be downloaded into, else default is ~/data/
sh data/scripts/VOC2012.sh # <directory>
```

### Training

You can start the training with one command. 

If you want to train the specific model listed in `model_zoo` in `train.py`, you can just link them as follows:

```sh
python train.py --model mssd
```

You can adjust the possibility for data augmentation in `data/voc0712.py` as well.

### Evaluation

To evaluate our trained network, you can simply enter the following command:

```sh
python eval.py --model mssd --trained_model weights/aug_mssd.pth
```

### Performance

**Aug-MSSD** on VOC2007 testset :

| mAP   | Extra Small | Small | Medium | Large | Extra Large |
| ----- | ----------- | ----- | ------ | ----- | ----------- |
| 79.62 | 23.40       | 57.14 | 87.13  | 94.77 | 92.49       |



### 