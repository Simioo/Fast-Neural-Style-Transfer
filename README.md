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
![Sebilj](https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/content-images/Screenshot%20from%202020-03-02%2018-17-50.png?raw=true)

Style image: <br>
![Starry Night](https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/style_images/starry_night_crop.jpg?raw=true)

Resulting image: <br>
![Starry Sebilj](https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/result-images/starry_sebilj.jpg?raw=true)


<img src='https://github.com/Simioo/Fast-Neural-Style-Transfer/blob/master/img/result-images/starry_sebilj.jpg?raw=true'  height="600" width="400">
