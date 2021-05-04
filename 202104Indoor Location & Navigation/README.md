## 2021.05.04


![image](https://user-images.githubusercontent.com/20613753/116960662-0e70fb00-acdc-11eb-9d97-0129e62c2752.png)
![image](https://user-images.githubusercontent.com/20613753/117076165-ec758800-ad70-11eb-8630-0ea52c7cdf0f.png)

![image](https://user-images.githubusercontent.com/20613753/117075744-4aee3680-ad70-11eb-99cc-a000e7beb0c1.png)
single positional indexer is out-of-bounds



## 2021.05.03
![image](https://user-images.githubusercontent.com/20613753/116872068-39157200-ac50-11eb-8395-77a16eb7b33e.png)  
このへんに複数の目的変数のモデルの構築の仕方が載ってる。  
  
https://developer.android.com/guide/topics/sensors/sensors_motion?hl=ja  
ここにandroidのmotionsenserの詳細が載ってる  
![image](https://user-images.githubusercontent.com/20613753/116872977-dcb35200-ac51-11eb-9338-2a6e7964871a.png)
  


## 2021.05.01
いまんのとこのリーク情報  
https://www.kaggle.com/c/indoor-location-navigation/discussion/234543  

・xyzのaccuracy、uncali、biasってなんだ？なんか補正かけないといけないかも。  
・磁場も補正かける  
・xとyの位置は目的変数が複数になっているので、それぞれを一体的に取り扱う。？  
　例えば8桁の数字として出しておいて、x=4桁、y=桁で、例の評価式で評価する。最後の段階でxとyを分割する。など。


## 2021.04.30
https://www.kaggle.com/rafaelcartenet/how-to-use  
範囲外を外れたらFalseを返すデータセット  
  
wifiポイントの高さと、スマホの高さの差を出すことで精度が上がりそう  

XYZは時間の経過に掛け算することで、移動の距離と方向を測ることができる。  
（最初の位置がわかればこのアプローチは非常に有効）  
上のデータセットと組み合わせれば、色々使えるかも知れない。

![image](https://user-images.githubusercontent.com/20613753/116643068-3b0ad700-a9ab-11eb-85a6-6c0e78750bf8.png)

![image](https://user-images.githubusercontent.com/20613753/116643037-24fd1680-a9ab-11eb-8f03-b7e6cb611f8e.png)

![image](https://user-images.githubusercontent.com/20613753/116642997-05fe8480-a9ab-11eb-8604-c2b09fe4deef.png)


ibeaconはルームレベルしか特定できない  
https://www.kaggle.com/iamleonie/ibeacon-feasibility-analysis

## 2020.04.29

![image](https://user-images.githubusercontent.com/20613753/116400976-a77bbe00-a865-11eb-8648-81acb09670cf.png)
・やること  
・timeの差は大事なはず（distance = time * speed ）→特徴量に入れる  
```
        train_meta_sub.loc[i,'wifi_ssid']=feature.wifi.iloc[0]['ssid']
        train_meta_sub.loc[i,'wifi_bssid']=feature.wifi.iloc[0]['bssid']
        train_meta_sub.loc[i,'wifi_rssi']=feature.wifi.iloc[0]['rssi']
        train_meta_sub.loc[i,'wifi_frequency']=feature.wifi.iloc[0]['frequency']
```

で指定したwifiは[0][1][2]・・・の順に近いwifiが入ってる




## コンペの概要  

Your smartphone goes everywhere with you—whether driving to the grocery store or shopping for holiday gifts. With your permission, apps can use your location to provide contextual information. You might get driving directions, find a store, or receive alerts for nearby promotions. These handy features are enabled by GPS, which requires outdoor exposure for the best accuracy. Yet, there are many times when you’re inside large structures, such as a shopping mall or event center. Accurate indoor positioning, based on public sensors and user permission, allows for a great location-based experience even when you aren’t outside.  
食料品店に車で行く場合でも、ホリデーギフトを買う場合でも、スマートフォンはどこにでも持ち運びできます。あなたの許可があれば、アプリはあなたの場所を使用してコンテキスト情報を提供できます。運転ルートを取得したり、お店を見つけたり、近くのプロモーションのアラートを受け取ったりする場合があります。これらの便利な機能はGPSによって有効になり、最高の精度を得るには屋外での露出が必要です。それでも、ショッピングモールやイベントセンターなどの大きな建物の中にいることはよくあります。公共のセンサーとユーザーの許可に基づく正確な屋内測位により、外出していないときでもロケーションベースの優れたエクスペリエンスが可能になります。  
  
Current positioning solutions have poor accuracy, particularly in multi-level buildings, or generalize poorly to small datasets. Additionally, GPS was built for a time before smartphones. Today’s use cases often require more granularity than is typically available indoors.  
現在のポジショニングソリューションは、特にマルチレベルの建物では精度が低いか、小さなデータセットへの一般化が不十分です。さらに、GPSはスマートフォンよりも前から構築されていました。今日のユースケースでは、通常、屋内で利用できるよりも細かい粒度が必要になることがよくあります。  

In this competition, your task is to predict the indoor position of smartphones based on real-time sensor data, provided by indoor positioning technology company XYZ10 in partnership with Microsoft Research. You'll locate devices using “active” localization data, which is made available with the cooperation of the user. Unlike passive localization methods (e.g. radar, camera), the data provided for this competition requires explicit user permission. You'll work with a dataset of nearly 30,000 traces from over 200 buildings.  
このコンテストでのあなたの仕事は、MicrosoftResearchと提携して屋内測位技術会社XYZ10から提供されたリアルタイムセンサーデータに基づいてスマートフォンの屋内位置を予測することです。ユーザーの協力を得て利用できる「アクティブな」ローカリゼーションデータを使用してデバイスを見つけます。パッシブローカリゼーション方法（レーダー、カメラなど）とは異なり、このコンテストで提供されるデータには、明示的なユーザー許可が必要です。 200を超える建物からの約30,000のトレースのデータセットを使用します。

If successful, you’ll contribute to research with broad-reaching possibilities, including industries like manufacturing, retail, and autonomous devices. With more accurate positioning, existing location-based apps could even be improved. Perhaps you’ll even see the benefits yourself the next time you hit the mall.
成功すれば、製造、小売、自律型デバイスなどの業界を含む、幅広い可能性を秘めた研究に貢献できます。より正確なポジショニングにより、既存のロケーションベースのアプリをさらに改善することができます。おそらく、次にモールに行くときに、自分でメリットを確認することもできます。

XYZ10 is a rising indoor positioning technology company in China. Since 2017, XYZ10 has been accumulating a privacy-sensitive indoor location dataset of WiFi, geomagnetic, and Bluetooth signatures with ground truths from nearly 1,000 buildings.

Microsoft Research is the research subsidiary of Microsoft. Its goal is to advance state-of-the-art computing and solve difficult world research-motivated competition problems through technological innovation in collaboration with academic, government, and industry researchers.
XYZ10は、中国で注目を集めている屋内測位技術企業です。 2017年以来、XYZ10は、プライバシーに配慮したWiFi、地磁気、Bluetoothの署名の屋内位置データセットを、1,000近くの建物からのグラウンドトゥルースとともに蓄積してきました。

Microsoft Researchは、Microsoftの研究子会社です。その目標は、最先端のコンピューティングを進歩させ、学術、政府、および業界の研究者と協力して技術革新を通じて、世界の研究に動機付けられた困難な競争問題を解決することです。

## 評価方法
https://www.kaggle.com/c/indoor-location-navigation/overview/evaluation  
  
## データの形
The dataset for this competition consists of dense indoor signatures of WiFi, geomagnetic field, iBeacons etc., as well as ground truth (waypoint) (locations) collected from hundreds of buildings in Chinese cities. The data found in path trace files (*.txt) corresponds to an indoor path between position p_1 and p_2 walked by a site-surveyor.

During the walk, an Android smartphone is held flat in front of the surveyors body, and a sensor data recording app is running on the device to collect IMU (accelerometer, gyroscope) and geomagnetic field (magnetometer) readings, as well as WiFi and Bluetooth iBeacon scanning results. A detailed description of the format of trace file is shown, along with other details and processing scripts, at this github link. In addition to raw trace files, floor plan metadata (e.g., raster image, size, GeoJSON) are also included for each floor.

A note on data quality: In the training files, you may find occasionally that a line is missing the ending newline character, causing it to run on to the next line. It is up to you how you want to handle this issue. This issue is not found in the test data.
このコンテストのデータセットは、WiFi、地磁気、iBeaconsなどの密な屋内署名と、中国の都市の何百もの建物から収集されたグラウンドトゥルース（ウェイポイント）（場所）で構成されています。パストレースファイル（* .txt）にあるデータは、サイト調査員が歩いた位置p_1とp_2の間の屋内パスに対応しています。

歩行中、Androidスマートフォンは調査員の体の前で平らに保持され、センサーデータ記録アプリがデバイス上で実行されてIMU（加速度計、ジャイロスコープ）と地磁気（磁力計）の測定値、およびWiFiとBluetoothを収集しますiBeaconスキャン結果。トレースファイルの形式の詳細な説明は、他の詳細および処理スクリプトとともに、このgithubリンクに表示されます。生のトレースファイルに加えて、フロアプランのメタデータ（ラスターイメージ、サイズ、GeoJSONなど）も各フロアに含まれています。

データ品質に関する注意：トレーニングファイルで、行の末尾の改行文字が欠落しているために、次の行に実行される場合があります。この問題をどのように処理するかはあなた次第です。この問題は、テストデータにはありません。  


train - training path files, organized by site and floor; each path files contains the data of a single path on a single floor  
test - test path files, organized by site and floor; each path files contains the data of a single path on a single floor, but without the waypoint (x, y) data; the task of this competition is, for a given site-path file, predict the floor and waypoint locations at the timestamps given in the sample_submission.csv file  
metadata - floor metadata folder, organized by site and floor, which includes the following for each floor:  
floor_image.png  
floor_info.json  
geojson_map.json  
sample_submission.csv - a sample submission file in the correct format; each has a unique id which contains a site id, a path id, and the timestamp within the trace for which to make a prediction; see the Evaluation page for the required integer mapping of floor names  
train-サイトとフロアごとに整理されたトレーニングパスファイル。各パスファイルには、1つのフロアにある1つのパスのデータが含まれています
test-サイトおよびフロアごとに編成されたテストパスファイル。各パスファイルには、単一フロアの単一パスのデータが含まれていますが、ウェイポイント（x、y）データは含まれていません。このコンテストのタスクは、特定のサイトパスファイルについて、sample_submission.csvファイルで指定されたタイムスタンプでフロアとウェイポイントの場所を予測することです。
メタデータ-サイトおよびフロアごとに編成されたフロアメタデータフォルダ。フロアごとに以下が含まれます。  
floor_image.png  
floor_info.json  
geojson_map.json  
sample_submission.csv-正しい形式のサンプル送信ファイル。それぞれに、サイトID、パスID、および予測を行うトレース内のタイムスタンプを含む一意のIDがあります。フロア名に必要な整数マッピングについては、評価ページを参照してください。
