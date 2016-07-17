# 課題８レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像  

画像の2値化を行い。その画像の連結部分にラベルをつける。

・画像の2値化  
IMG = ORG > 128; % 閾値128で二値化  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  

閾値を輝度値128に設定し、2値化を行った結果を図2に示す。  
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai8_128.jpg)
図2 2値化画像  

・ラベル付け
関数bwlabelnを用いてラベル付けを行った結果を図3示す。  

IMG = bwlabeln(IMG);  
imagesc(IMG); colormap(jet); colorbar; % 画像の表示  
pause;  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai8_label.jpg)
図3 ラベル付けを行った画像 
