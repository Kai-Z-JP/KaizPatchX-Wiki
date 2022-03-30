# 追加された機能
## 目次
- [追加された機能](#追加された機能)
  - [目次](#目次)
  - [機能解説](#機能解説)
    - [モデルパックロードのマルチスレッド化](#モデルパックロードのマルチスレッド化)
    - [乗客の視点追従](#乗客の視点追従)
    - [ノッチ/ブレーキ段数カスタム](#ノッチブレーキ段数カスタム)
    - [加減速度カスタム](#加減速度カスタム)
      - [実装方法](#実装方法)
    - [踏切・信号・転轍機・照明・改札・車止め・車両モデルのスポイト](#踏切信号転轍機照明改札車止め車両モデルのスポイト)
    - [踏切・信号・転轍機・照明・標識モデルの1度刻み設置](#踏切信号転轍機照明標識モデルの1度刻み設置)
    - [レール変形操作方法の選択](#レール変形操作方法の選択)
    - [レール・ワイヤー描画距離の延長](#レールワイヤー描画距離の延長)
    - [コマンドのタブ補完](#コマンドのタブ補完)
    - [FlySpeedコマンド](#flyspeedコマンド)
    - [車内アナウンスの編成内全車両での再生](#車内アナウンスの編成内全車両での再生)
    - [後退機能](#後退機能)
    - [同時再生数の拡張](#同時再生数の拡張)
    - [踏切・転轍機・照明・改札のオフセット](#踏切転轍機照明改札のオフセット)
    - [クリエイティブモード時のレールクラフト時間削除](#クリエイティブモード時のレールクラフト時間削除)
    - [レンチ吸い付き切替](#レンチ吸い付き切替)
    - [MCtrlコマンドのタブ補完](#mctrlコマンドのタブ補完)
    - [信号･看板のオフセット](#信号看板のオフセット)
    - [モデルのロード状況の数値表示](#モデルのロード状況の数値表示)
    - [サーバースクリプトからの加減速度制御](#サーバースクリプトからの加減速度制御)
      - [実装方法](#実装方法-1)
    - [一部のES6構文のサポート](#一部のes6構文のサポート)
    - [TestTrainに専用テクスチャを追加](#testtrainに専用テクスチャを追加)
    - [Webp形式の画像のサポート](#webp形式の画像のサポート)
    - [TileEntityOrnamentのオフセット](#tileentityornamentのオフセット)
    - [古い形式のコネクタのサポート](#古い形式のコネクタのサポート)
    - [コネクタのオフセット](#コネクタのオフセット)
    - [台車の強制チャンクロード](#台車の強制チャンクロード)
    - [/rtm summon コマンド](#rtm-summon-コマンド)
      - [使用例](#使用例)
    - [アイテムにDataMap/Offsetの保存情報の表示](#アイテムにdatamapoffsetの保存情報の表示)
    - [Fキー押下でCustomButtonの情報の編成内全車両への送信](#fキー押下でcustombuttonの情報の編成内全車両への送信)

## 機能解説
### モデルパックロードのマルチスレッド化
- [x] KaizPatchNWS: 1.7.10.10.1  
  モデルパックをロードするときに、同時に複数のスレッドでロードするようにします。
### 乗客の視点追従
- [x] KaizPatchNWS: 1.7.10.12  
  列車に乗車している乗客の視点が列車の方向に追従します。
### ノッチ/ブレーキ段数カスタム
- [x] KaizPatchNWS: 1.7.10.12  
  車両モデルごとにノッチ/ブレーキ段数をjsonでカスタムできます。
### 加減速度カスタム
- [x] KaizPatchNWS: 1.7.10.12  
  車両モデルごとに加減速度をjsonで固定値にカスタムできます。
  #### 実装方法
  ```
  ノッチ段数での最高速度(ノッチ段数をここで決定)
  "maxSpeed": [ 1段, 2段, 以下無限(notDisplayCabがfalseの場合は5段固定) ],
  加速度
  "accelerateions": [ 1段, 2段, 以下無限(notDisplayCabがfalseの場合は5段固定) maxSpeedの個数と同値],
  減速度(ブレーキ段数をここで決定)
  "deccelerations": [惰性, -1段, -2段, 以下無限(notDisplayCabがfalseの場合は-8段固定)],
  ```

### 踏切・信号・転轍機・照明・改札・車止め・車両モデルのスポイト
- [x] KaizPatchNWS: 1.7.10.12  
  ホイールクリックで踏切・信号・転轍機・照明・改札・車止め・車両モデルのスポイトを行います。
### 踏切・信号・転轍機・照明・標識モデルの1度刻み設置
- [x] KaizPatchNWS: 1.7.10.12  
  スニーク状態で踏切・信号・転轍機・照明・標識モデルを1度刻み設置できます。
### レール変形操作方法の選択
- [x] KaizPatchNWS: 1.7.10.12  
  レールの変形を操作する方法をレンチ方式(1.7.10)とGUI方式(1.12.2)から選択できます。
### レール・ワイヤー描画距離の延長
- [x] KaizPatchNWS: 1.7.10.13  
  レール・ワイヤーの描画が見切れないようになります。
### コマンドのタブ補完
- [x] KaizPatchX: 1.1RC1  
  コマンド入力時にタブ補完が行えます。
### FlySpeedコマンド
- [x] KaizPatchX: 1.1RC1  
  /rtm flyspeed [0.0-10.0] でFlySpeedを変更できます。
### 車内アナウンスの編成内全車両での再生
- [x] KaizPatchX: 1.1RC1  
  車内アナウンスを再生時に編成内全車両で再生します。
### 後退機能
- [x] KaizPatchX: 1.1RC1  
  逆転ハンドルを後に設定時に加速をすると後退します。
### 同時再生数の拡張
- [x] KaizPatchX: 1.1RC2  
  音声の同時再生数を1024まで拡張します。
### 踏切・転轍機・照明・改札のオフセット
- [x] KaizPatchX: 1.2RC1  
  踏切・転轍機・照明・改札のオフセットを設定できます。
### クリエイティブモード時のレールクラフト時間削除
- [x] KaizPatchX: 1.2RC1  
  レール作業台でクラフト時のレールクラフト時間を削除します。
### レンチ吸い付き切替
- [x] KaizPatchX: 1.2RC2  
  マーカーでの調整時にハンドルが反対側のレールに吸い付くかを切り替えできます。
### MCtrlコマンドのタブ補完
- [x] KaizPatchX: 1.3RC1  
  MCtrlコマンド入力時にタブ補完が行えます。
### 信号･看板のオフセット
- [x] KaizPatchX: 1.3RC1.1  
  信号･看板のオフセットを設定できます。
### モデルのロード状況の数値表示
- [x] KaizPatchX: 1.3.0-RC2  
  モデルのロード状況を数値表示します。
### サーバースクリプトからの加減速度制御
- [x] KaizPatchX: 1.4.0-beta1  
  スクリプトからの加減速度制御を行えます。

  #### 実装方法
  ```js
  //これをサーバースクリプトに追加してください。onUpdateが無い場合、ダミーで空のonUpdateを追加してください。
  //fixRTM(2.0.20以降)でも同じように実装できます
  /*
  function onUpdate(entity, scriptExecuter) {
      //dummy
  }
  */
  function getAcceleration(train, prevSpeed) {
      /*
      ModelTrainのjson内に
      "useVariableAcceleration": true,
      を追加してください
      trainはEntityTrainBase
      prevSpeedは1Tick前のスピード(m/tick) 時速への変換は72倍
      設定したい加速度をN(km/h/s)としたとき返り値はN * 0.0006944にしてください
      返り値は正の値にしてください。
      */
      return N(km/h/s) * 0.0006944;
  }

  function getDeceleration(train, prevSpeed) {
      /*
      ModelTrainのjson内に
      "useVariableDeceleration": true,
      を追加してください
      trainはEntityTrainBase
      prevSpeedは1Tick前のスピード(m/tick) 時速への変換は72倍
      設定したい減速度をN(km/h/s)としたとき返り値はN * 0.0006944にしてください
      返り値は負の値にしてください。
      */
      return N(km/h/s) * 0.0006944;
  }
  ```
### 一部のES6構文のサポート
- [x] KaizPatchX: 1.4.0-beta1  
  一部のES6構文をサポートします。
### TestTrainに専用テクスチャを追加
- [x] KaizPatchX: 1.4.0-beta1  
  TestTrainに専用テクスチャを追加します。
### Webp形式の画像のサポート
- [x] KaizPatchX: 1.4.0-beta3  
  テクスチャにWebp形式の画像を使用できるようになります。
### TileEntityOrnamentのオフセット
- [x] KaizPatchX: 1.4.0-beta3  
  TileEntityOrnamentのオフセットを設定できます。
### 古い形式のコネクタのサポート
- [x] KaizPatchX: 1.4.0-beta3    
  RTM1.7.10.34以前の古い形式のコネクタをサポートします。
### コネクタのオフセット
- [x] KaizPatchX: 1.4.0-beta3  
  コネクタのオフセットを設定できます。
### 台車の強制チャンクロード
- [x] KaizPatchX: 1.4.1  
  台車を強制的にロードします。
### /rtm summon コマンド
- [x] KaizPatchX: 1.4.2  
  /rtm summonで車両を出現させられます。
  #### 使用例
  /rtm summon [Type]:[SubType] [ModelName] [x] [y] [z] \<yaw> \<JsonNBT>  
  yawは線路に合わせて自動で補正されます。  
  また、yawとJsonNBTは任意です(ただし、JsonNBTを設定する場合はyawの設定も必要です)  
  デフォルトの223系先頭車をx: 0, y: 4, z: 0にyaw: 0で色にffffff(白)、DataMapにtestKey=(String)testValue、CustomNameにTestNameを設定して召喚する場合の例
  ```
  /rtm summon ModelTrain:EC 223h 0 4 0 0 {Color:16777215,DataMap:{DataList:[0:{Type:"String",Data:"testValue",Flag:3,Name:"testKey",},],},Name:"TestName",}
  ```
  現時点でTypeにはModelTrainが、SubTypeにはEC, DC, TC, CC, Testが設定可能です。

### アイテムにDataMap/Offsetの保存情報の表示
- [x] KaizPatchX: 1.4.5  
  アイテムにDataMap/Offsetの保存情報の表示を追加します。
### Fキー押下でCustomButtonの情報の編成内全車両への送信
- [x] KaizPatchX: 1.4.5  
  CustomButtonの情報の編成内全車両への送信をFキー押下で行えます。