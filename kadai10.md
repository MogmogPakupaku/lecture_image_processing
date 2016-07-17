# 課題１０レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像

３つのエッジ抽出法を元画像にそれぞれ適用し結果を観察する。　　

・プレウィット法  
IMG = edge(ORG,'prewitt'); % エッジ抽出（プレウィット法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止  

結果を図2に示す　　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai10_prewitt.jpg)  
図2 プレウィット法によるエッジ抽出

・ソベル法
IMG = edge(ORG,'sobel'); % エッジ抽出（ソベル法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止  

結果を図3に示す　　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai10_sobel.jpg)  
図3 ソベル法によるエッジ抽出

・キャニー法  
IMG = edge(ORG,'canny'); % エッジ抽出（キャニー法）  
imagesc(IMG); colormap('gray'); colorbar;% 画像表示  
pause; % 一時停止  

結果を図4に示す　　
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai10_canny.jpg)  
図4 キャニー法によるエッジ抽出

結果を比較すると、プレウィット法とソベル法は陸地と水面の境目が輪郭として分かりやすく、似たような抽出結果となった。キャニー法では陸地と水面の輪郭はわかりにくいが、雲の輪郭がはっきりと抽出できていることがわかる。
