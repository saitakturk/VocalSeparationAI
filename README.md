# VocalSeparationAI
This repo is self-learning project that the music and its local converted to relative spektograms, then using these spectograms, the vocal seperation AI is trained.

## Some Test Results ##

| Music   | Vocal   | AI Output |
| :------------ |:---------------:| -----:|
| ![](https://github.com/saitakturk/VocalSeparationAI/blob/master/photo_2019-03-22_03-37-53.jpg)     | ![](https://github.com/saitakturk/VocalSeparationAI/blob/master/photo_2019-03-22_03-37-49.jpg) | ![](https://github.com/saitakturk/VocalSeparationAI/blob/master/photo_2019-03-22_03-37-45.jpg) |
| [Music Listen ](https://vocaroo.com/i/s1swG023k5yP)     | [Vocal Listen ](https://vocaroo.com/i/s1WRhavNNT0U)        |  [AI Output Listen](https://vocaroo.com/i/s1QlJP1hGwCi)  |



## The dataset ##

* I used DSD100 dataset to get music and vocal.
  * [The Dataset ](https://sigsep.github.io/datasets/dsd100.html)
* The musics and vocals is splitted 5 sec parts and converted to spectograms. The dataset I created with spectograms
  * [The Spectogram Dataset](https://drive.google.com/open?id=1r47OKZrPbv1dYi-p6-IbuLkYs2SUZsvo)


## Tools ## 

* I used provided repo to convert from music to spectogram and spectogram to music
  * [Spectogram Program](http://krajj7.github.io/spectrogram/)
* I used pix2pix-tensorflow implementation to train the model
  * [Pix2Pix2](https://github.com/affinelayer/pix2pix-tensorflow)
  
## Preprocessing Details ##
1 - The musics and vocals is splitted to 5 sec music parts.
2 - The 5 sec parts is converted to spectogram images. Changed Values to get 255x256 images : 
  * Pixels per second : 51
  * Bandwitdh         : 205
3 - 1 pixel width is added end of the width( Don't put start ) to get image size 256x256 images.
4 - The parts that do not contain vocals is removed from dataset via removing the images has only 0 pixel values.


## Training Details ##

* I trained 10 epochs in pix2pix implementation.

## Further Improvements and Limitations ## 

I will update this part 

* pix2pixHD.
* transparency problem of spectograms.
