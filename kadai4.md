# 課題４レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

つぎに図１のヒストグラムを表示する。ヒストグラムを表示するために　　

imhist(ORG);　　

と記述すればよい。ヒストグラムを図2に示す。

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai4_1.jpg)  
図2 風景画ヒストグラム

この画像は比較的、輝度値が低い方に偏っていることがわかる。　　

次に画像を見て輝度値が高そうなもののヒストグラムを観察する。　　
ここでは白毛馬として有名であったのユキチャンの画像を使用する。画像を図3にヒストグラムを図４にそれぞれ示す。　　
画像URL：http://poclog.cocolog-nifty.com/book/images/horse/blue/blue_0522026.jpg　　

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/yukityan.jpg)  
図3 白毛馬

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai4_yukityan.jpg)  
図4 ヒストグラム





