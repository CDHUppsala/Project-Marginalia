# Marginalia and Machine Learning

PyTorch implementation of a Handwritten Text Recognition (HTR) system that focuses on automatic detection and recognition of handwritten marginalia texts i.e., text written in margins or handwritten notes. Faster R-CNN network is used for detection of marginalia and [AttentionHTR](https://github.com/dmitrijsk/AttentionHTR) is used for word recognition. The data comes from early book collections (printed) found in the Uppsala University Library, with handwritten marginalia texts.

This is a work under progress. For more details, refer to our paper at [arXiv](https://arxiv.org/pdf/2303.05929.pdf).

## Dependencies 

To run the code, run the following

```
python3 -m venv marginalia-env
source marginalia-env/bin/activate
pip install --upgrade pip
python3 -m pip install -r Project-Marginalia/requirements.txt
```


## Demo of our pre-trained model

### Marginalia detection
* Download the pre-trained model `faster_r_cnn_weights.pt` from [here](https://drive.google.com/drive/folders/1k2CxBbIyVp_7iq5-vQgBsP5nOtMSlSIj?usp=sharing) and place it into `/Project-Marginalia/model/`.
* Create the folder `Project-Marginalia/model/data/test_images/` and place in them the test images.
* Create the folder `Project-Marginalia/model/results/`
* To detect and visualize the marginalias, run ```python3 model/test.py```

### Marginalia Segmentation
* If you want to use your model on your own set of images, use the image_to_bboxes.py script. In it you will have to add the path to your model, folder of your dataset, and the location where you want the predicted marginalia to be saved. Then run 'python3 image_to_bboxes.py'.
* If you want to segment a set of marginalia to individual words, use the marginalia_to_words.py script. In it you will have to add the path to a folder containing images of predicted marginalia, as well as the folder where you want the results to be saved. Then run 'python3 marginalia_to_words.py'.

### Word recognition using AttentionHTR
* To recognise the words with AttentionHTR, follow the instructions from [here](https://github.com/dmitrijsk/AttentionHTR)

  <center><img src="https://user-images.githubusercontent.com/73716649/224288003-be1a65da-8e85-438b-b78a-ce5662fbf5f3.png" height="400" > 
 

## Acknowledgements
* This work has been partially supported by the Matariki Network Initiation Grant: "Marginalia and Machine Learning: a Study of Durham University and Uppsala University Marginalia Collections".
* The computations/data handling were enabled by resources provided by the Swedish National Infrastructure for Computing (SNIC) at Chalmers Centre for Computational Science and Engineering (C3SE) partially funded by the Swedish Research Council through grant agreement no. 2018-05973, project Dnr: SNIC 2022/22-1084.
* The authors would like to thank the Centre for Digital Humanities Uppsala ([CDHU](https://www.abm.uu.se/cdhu-eng)) and Uppsala University Library ([Alvin](https://www.alvin-portal.org/alvin/view.jsf?pid=alvin-organisation%3A16&dswid=-1828)) for offering the dataset.
* This project was done as part of the Data Science project course, team: Adam Axelsson, Liang Cheng, Jonas Frankemölle, and Ekta Vats (supervisor).


## References
[1]: Dmitrijs Kass and Ekta Vats. "AttentionHTR: Handwritten Text Recognition Based on Attention Encoder-Decoder Networks." *International Workshop on Document Analysis Systems*. Springer, Cham, 2022. [Link](https://link.springer.com/chapter/10.1007/978-3-031-06555-2_34) [Code](https://github.com/dmitrijsk/AttentionHTR)

## Contact

Ekta Vats (ekta.vats@abm.uu.se)

Adam Axelsson (adam.axelsson.4529@student.uu.se)

Liang Cheng (chengliang653@gmail.com)

Jonas Frankemölle (frankemoelle.jonas@gmail.com)
