# 課題３レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

kadai2で2階調画像を生成した。このときの閾値を変更したときの変化を見る。

閾値を輝度値=64と設定した時いかのようなコードとなる。

IMG = ORG > 64; 
imagesc(IMG); colormap(gray); colorbar;  
pause; 

閾値を64としたときの結果を図２に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_64.jpg)  
図2 閾値64の2階調画像 

閾値を輝度値=96と設定した時いかのようなコードとなる。

IMG = ORG > 96; 
imagesc(IMG); colormap(gray); colorbar;  
pause; 

閾値を96としたときの結果を図３に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_96.jpg)  
図３ 閾値96の2階調画像 

閾値を輝度値=128と設定した時いかのようなコードとなる。

IMG = ORG > 128; 
imagesc(IMG); colormap(gray); colorbar;  
pause; 

閾値を128としたときの結果を図４に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_128.jpg)  
図４ 閾値128の2階調画像   

 

閾値を輝度値=192と設定した時いかのようなコードとなる。

IMG = ORG > 192; 
imagesc(IMG); colormap(gray); colorbar;  
pause; 

閾値を192としたときの結果を図５に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_192.jpg)  
図５ 閾値192の2階調画像   

閾値を輝度値=216と設定した時いかのようなコードとなる。

IMG = ORG > 216; 
imagesc(IMG); colormap(gray); colorbar;  
pause; 

閾値を216としたときの結果を図６に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_216.jpg)  
図６ 閾値216の2階調画像   
