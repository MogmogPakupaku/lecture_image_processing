# 課題７レポート

風景画を現画像とする．この画像は縦1080画素，横1920画素による長方形のディジタルカラー画像である．

ORG=imread('http://www.v3wall.com/wallpaper/1920_1080/1009/1920_1080_201009260121042155462.jpg'); % 原画像の入力  
ORG = rgb2gray(ORG); colormap(gray); colorbar;%rgb2gray()でグレースケール化  
imagesc(ORG); axis image; % 画像の表示  
imhist(ORG); % 濃度ヒストグラムを生成、表示  
pause;  

によって，原画像を読み込み，グレースケール化を行い、表示した結果を図１に示す．ヒストグラムを図2に示す。  

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai2_gryorg.jpg)  
図1 原画像  
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai7_gryorg_histogram.jpg)  
図2 濃度ヒストグラム  

・ダイナミックレンジの拡大　 
ORG = double(ORG)
mn = min(ORG(:)); % 濃度値の最小値を算出 
mx = max(ORG(:)); % 濃度値の最大値を算出  
ORG = (ORG-mn)/(mx-mn)*255;  
imagesc(ORG); colormap(gray); colorbar; % 画像の表示  
pause;  
ORG = unit8(ORG); % この行について考察せよ  
imhist(ORG); % 濃度ヒストグラムを生成、表示  

まずORGをdouble型に変換することで少数地を扱えるようにする。
次に濃度の最大値、最小値を検出し、レンジの幅を検出した最小値から255までに変更する。  
画像の表示を行い、小数値を8bitの整数地に戻すunit8を使用する。  
その後ヒストグラムを表示する。  

レンジ変換を行った画像を図3にヒストグラムを図4に示す。  
![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai7_dyna.jpg)  
図3 変換後のグレースケール画像 

![原画像](https://github.com/MogmogPakupaku/lecture_image_processing/blob/master/image/kadai7_dyna_histogram.jpg)  
図4 変換後の濃度ヒストグラム  

ダイナミックレンジ変換後の濃度ヒストグラムを見ると、変化していないことがわかる。　　
これは元画像の濃度値に低い数値が存在していたためであった。　　
現在はデジタルカメラが自動的にダイナミックレンジの補正をかけてしまうため、露出過多の画像が探しにくい  
それだけに、この技術が普及していることが理解できた。
