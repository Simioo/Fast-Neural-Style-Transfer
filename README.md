# Fast-Neural-Style-Transfer
Deep Learning model for transferring the artistic style of one image to another, while preserving the original content of the other image. 

Link to Google Colab Notebook: https://colab.research.google.com/drive/1AOiWHk1Qnp3WKKoTvkToJzMi93q0gYJA


This project is based on the following research papers:

A Neural Algorithm of Artistic Style by Leon A. Gatys, Alexander S. Ecker, Matthias Bethge
Perceptual Losses for Real-Time Style Transfer and Super-Resolution by Justin Johnson, Alexandre Alahi, Li Fei-Fei
Instance Normalization: The Missing Ingredient for Fast Stylization by Dmitry Ulyanov, Andrea Vedaldi, Victor Lempitsky

The goal of the project is to build and train a deep learning model capable of transferring the artistic style of one image to another, while preserving the original content of the other image.
We train one network per style using MS-COCO dataset which contains around 70k images. Previous work on this topic of Leon A. Gatys et al. used optimization approach, where content image pixels
were directly modified to lower the values of both style and content loss functions until we get satisfying image. The problem with that approach is that it doesn't work in real time. Depending
on the hardware, it could take even 10-15 minutes to generate one image. To generate another image, we have to start this process all over again. The idea that Justin Johnson et al. presented
in their paper is that we could train the deep neural network which could perform this task in real time once trained (less than 1 second).  This is illustrated in the example below:

Content image: <br>
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/content-images/Screenshot%20from%202020-03-02%2018-17-50.png?raw=true'  height="400" width="600">

Style image: <br>
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/style_images/starry_night_crop.jpg?raw=true'  height="500" width="600">

Resulting image: <br>
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/result-images/starry_sebilj.jpg?raw=true'  height="400" width="600">


We can train deep neural network for any style, so we'll give more examples of style images here: <br>

<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/style_images/candy.jpg?raw=true'  height="400" width="300">
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/style_images/mosaic.jpg?raw=true'  height="300" width="400">

The images that we get as a result are shown below:

Content image:
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/content-images/chicago.jpg?raw=true'  height="400" width="600">

Resulting image:
<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/result-images/chicago_mosaic.png?raw=true'  height="400" width="600">

<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/result-images/88220537_843516089454988_1869737549010829312_n.png?raw=true'  height="500" width="700">
