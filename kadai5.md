# 課題5レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

ここでは判別分散法を用いた画像の2値化を行う。　

H = imhist(ORG); %ヒストグラムのデータを列ベクトルEに格納　　
myu_T = mean(H);　
max_val = 0;　　
max_thres = 1;　　
for i=1:255　　
C1 = H(1:i); %ヒストグラムを2つのクラスに分ける　　
C2 = H(i+1:256);　　
n1 = sum(C1); %画素数の算出　　
n2 = sum(C2);　　
myu1 = mean(C1); %平均値の算出　　
myu2 = mean(C2);　　
sigma1 = var(C1); %分散の算出  
sigma2 = var(C2);  
sigma_w = (n1 *sigma1+n2*sigma2)/(n1+n2); %クラス内分散の算出  
sigma_B = (n1 *(myu1-myu_T)^2+n2*(myu2-myu_T)^2)/(n1+n2); %クラス間分散の算出  
if max_val<sigma_B/sigma_w  
max_val = sigma_B/sigma_w; 
max_thres =i;  
end;  
end;  

IMG = ORG > max_thres;  
imagesc(IMG); colormap(gray); colorbar;  
pause;  

結果を図2に示す。　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai5_1.jpg)  
図2 判別分析法を用いた2値化

閾値128で2値化した結果を図3に示す。　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai3_128.jpg)  
図3 閾値128での2値化
