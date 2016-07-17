# 課題９レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

グレースケール化した画像にノイズを添付し、それをフィルタをつかい除去する。

・ノイズ添付  
ORG = imnoise(ORG,'salt & pepper',0.02); % ノイズ添付  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  
pause;imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止  

mtlabに搭載されている関数imnoiseを使用してノイズの添付を行う。ノイズの種類はsalt & pepperとし密度は0.02に設定する。  
結果を図2に示す　　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai9_01.jpg)  
図2 ノイズ添付

・ノイズ除去  
IMG = filter2(fspecial('average',3),ORG); % 平滑化フィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  
pause;  
IMG = medfilt2(ORG,[3 3]); % メディアンフィルタで雑音除去  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  
pause;  
f=[0,-1,0;-1,5,-1;0,-1,0]; % フィルタの設計  
IMG = filter2(f,IMG,'same'); % フィルタの適用  
imagesc(IMG); colormap(gray); colorbar; % 画像の表示  
pause;  

各種フィルタを適用した結果を図3､図4、図5にそれぞれ示す。

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai9_02.jpg)  
図3 平滑化フィルタ適用  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai9_03.jpg)  
図4 メディアンフィルタ適用

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai9_04.jpg)  
図5 フィルタ適用

フィルタを適用した結果、大部分のノイズが除去されていることがわかる。





