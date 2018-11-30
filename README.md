# GAN-coupon-art

Pytorch implementation of msg-net and style transfer. 


### My Idea
 ![](experiments/images/content/use_case1.png)
 
 ![](experiments/images/content/use_case2.png)

**Tabe of content**

* [Real-time Style Transfer using MSG-Net](#msg-net)
	- [Stylize Images using Pre-trained Model](#stylize-images-using-pre-trained-msg-net)
	- [Train Your Own MSG-Net Model](#train-your-own-msg-net-model)
* [Slow Neural Style Transfer](#neural-style)


### Stylize Images Using Pre-trained MSG-Net

0. Download the pre-trained model

	```
	git clone https://gitlab.catmktg.com/amishra/GAN-coupon-art.git
	cd GAN-coupon-art/experiments
	bash models/download_model.sh
	```
0. Camera Demo  

	```
	python camera_demo.py demo --model models/21styles.model
	```
	![](experiments/avi.png)
0. Test the model  

	```
	python main.py eval --content-image images/content/venice-boat.jpg --style-image images/21styles/candy.jpg --model models/21styles.model --content-size 1024
	```
* If you don't have a GPU, simply set `--cuda=0`. For a different style, set `--style-image path/to/style`.
	If you would to stylize your own photo, change the `--content-image path/to/your/photo`. 
	More options:

	* `--content-image`: path to content image you want to stylize.
	* `--style-image`: path to style image (typically covered during the training).
	* `--model`: path to the pre-trained model to be used for stylizing the image.
	* `--output-image`: path for saving the output image.
	* `--content-size`: the content image size to test on.
	* `--cuda`: set it to 1 for running on GPU, 0 for CPU.

<img src ="images/1.jpg" width="260px" /> 
<img src ="images/2.jpg" width="260px" />
<img src ="images/3.jpg" width="260px" />
<img src ="images/4.jpg" width="260px" />
<img src ="images/5.jpg" width="260px" />
<img src ="images/6.jpg" width="260px" />
<img src ="images/7.jpg" width="260px" />
<img src ="images/8.jpg" width="260px" />
<img src ="images/9.jpg" width="260px" />


<img src ="experiments/avi1.jpg" width="260px" /> 
<img src ="experiments/avi2.jpg" width="260px" />
<img src ="experiments/avi3.jpg" width="260px" />
<img src ="experiments/avi4.jpg" width="260px" />
<img src ="experiments/avi5.jpg" width="260px" />
<img src ="experiments/avi6.jpg" width="260px" />
<img src ="experiments/avi7.jpg" width="260px" />
<img src ="experiments/avi8.jpg" width="260px" />
<img src ="experiments/avi9.jpg" width="260px" />

### Train Your Own MSG-Net Model  
0. Download the COCO dataset

	```
	bash dataset/download_dataset.sh
	```
0. Train the model  

	```
	python main.py train --epochs 4
	```
* If you would like to customize styles, set `--style-folder path/to/your/styles`. More options:
	* `--style-folder`: path to the folder style images.
	* `--vgg-model-dir`: path to folder where the vgg model will be downloaded.
	* `--save-model-dir`: path to folder where trained model will be saved.
	* `--cuda`: set it to 1 for running on GPU, 0 for CPU.

## Neural Style  

[Image Style Transfer Using Convolutional Neural Networks](http://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) by Leon A. Gatys, Alexander S. Ecker, and Matthias Bethge.


```
python main.py optim --content-image images/content/venice-boat.jpg --style-image images/21styles/candy.jpg
```
* `--content-image`: path to content image.
* `--style-image`: path to style image.
* `--output-image`: path for saving the output image.
* `--content-size`: the content image size to test on.
* `--style-size`: the style image size to test on.
* `--cuda`: set it to 1 for running on GPU, 0 for CPU.

<img src ="experiments/images/content/c1_1.jpg" width="780px" /> 
<br/>
<img src ="experiments/c1_1.jpg" width="260px" /> 
<img src ="experiments/c1_2.jpg" width="260px" />
<img src ="experiments/c1_3.jpg" width="260px" />
<img src ="experiments/c1_4.jpg" width="260px" />
<img src ="experiments/c1_5.jpg" width="260px" />
<img src ="experiments/c1_6.jpg" width="260px" />
<img src ="experiments/c1_7.jpg" width="260px" />
<img src ="experiments/c1_8.jpg" width="260px" />
<img src ="experiments/c1_9.jpg" width="260px" />
<img src ="experiments/c1_10.jpg" width="260px" />
<img src ="experiments/c1_11.jpg" width="260px" />
<img src ="experiments/c1_12.jpg" width="260px" />