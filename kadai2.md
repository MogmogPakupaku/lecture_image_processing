# 課題２レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

2階調画像を生成するには閾値を設定し,それ未満を０,閾値以上を１と設定すればよい.
閾値を輝度値=128と設定した時いかのようなコードとなる。

IMG = ORG>128;%閾値
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

2階調画像生成の結果を図２に示す．

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_1.jpg)  
図2 1/2サンプリング

4階調画像を生成するには閾値を3つ設定し,それ未満を０,閾値以上を１としたものを足し合わせればよい.

IMG0 = ORG>64;
IMG1 = ORG>128;
IMG2 = ORG>192;
IMG = IMG0 + IMG1 + IMG2;%
imagesc(IMG); colormap(gray); colorbar;  axis image;
pause;

ここでは閾値を64,128,192と設定し、それらの場合で2値化を行っている。これらを足し合わせることで
輝度値が        64以下を0
         65以上128以下を1
        129以上192以下を2
        　      193以上を3とした4階調画像を生成することができる生成結果を図３示す 。

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_2.jpg)  
図3 1/4サンプリング

1/8から1/32サンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図４～６に示す．

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai01_3.jpg)  
図4 1/8サンプリング

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai01_4.jpg)  
図5 1/16サンプリング

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai01_5.jpg)  
図6 1/32サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
