# 課題6レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

ここでは閾値128による2値化とディザ法による２値化の比較を行う。　　

・閾値128による2値化
IMG = ORG>128; % 128による二値化　　
imagesc(IMG); colormap(gray); colorbar; % 画像の表示　　
結果を図2に示す。  
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai6_128.jpg)    
図2 閾値128による2値化画像

・ディザ法による２値化　　
IMG = dither(ORG); % ディザ法による二値化　　
imagesc(IMG); colormap(gray); colorbar; % 画像の表示　　
結果を図3に示す。　　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai6_dither.jpg)  
図3 ディザ法による2値化画像
  
比較するとディザ法は画像が多階調にみえるため、元画像と比較しても陸と水面の境目が変わりなく、わかりやすい。


