# omotebako-system
omotebako-system は、クラウドからほぼ遮断されたクローズドなエッジネットワーク環境において、エッジアプリケーションとしてクラウドから独立した機能群（エッジAI、IoT機能を含む）を提供する、エッジアプリケーション「OMOTE-Bako」のリソースをまとめたレポジトリです。    
omotebako-system は、先進的なマイクロサービスアーキテクチャとエッジコンピューティングアーキテクチャを含む、Latona の 先進技術をエッジデバイスに実装した実用エッジアプリケーションシステムです。  
omotebako-system は、Latonaより宿泊業向けにリリース済のシステムであり、今後、小売業、製造業、物流業、その他の店舗業向けに、機能を拡張してリリース予定の、エッジアプリケーション群の総称です。    


## 動作環境

omotebako-system は、AION のプラットフォーム上での動作を前提としています。  

* OS: Linux OS  

* CPU: ARM/AMD/Intel  

* Kubernetes  

* AION のリソース  


## omotebako-system の アーキテクチャ  
![OMOTE-Bakoアーキテクチャ](documents/omotebako_architecture_20211016.drawio.png)    


## 宿泊業向け の omotebako-system に 含まれる機能（＝マイクロサービス）  
宿泊業向け の omotebako-system には、次の機能が含まれています。    
各機能は、マイクロサービスとして Kubernetes の Pod 上で 動作します。  

* Microsoft Azure を利用した 顔認証機能（マイクロサービスとして機能動作）   

* 顔情報と関連付けられた顧客データベース（マイクロサービスとして機能動作）  

* チェックイン/チェックアウト・予約管理・宿泊管理・客室管理・マスタ管理機能（マイクロサービスとして機能動作）  

* 顧客の宿泊カレンダー機能（マイクロサービスとして機能動作）  

* 予約サイトからの予約データ連携機能（マイクロサービスとして機能動作）　　

* USBメモリーからのデータ連携機能（マイクロサービスとして機能動作）　　

* デスクトップサーバー向けUIフロントエンド（マイクロサービスとして機能動作）　　

* モバイル端末向けUIフロントエンド（マイクロサービスとして機能動作）　　

* モバイル端末向けロードバランサー（マイクロサービスとして機能動作）  

* UIバックエンド（マイクロサービスとして機能動作）　　

* 主にUIフロントエンドとUIバックエンドのためのキャッシュDB（マイクロサービスとして機能動作）  

* 認証モジュール（マイクロサービスとして機能動作）  

* マスタDBと各テーブル（DBと各テーブルは分離可能で、それぞれマイクロサービスとして機能動作）  

* DBバックアップ（マイクロサービスとして機能動作）  

* アプリケーションログ（Golang, Pythonランタイム対応）の入出力、DBへの更新（マイクロサービスとして機能動作）   

* アプリケーションログ用のDB（マイクロサービスとして機能動作）   

* アプリケーションログ の Azure IoT Hub への連携（マイクロサービスとして機能動作）  

* カメラ画像のブラウザへのストリーミング機能 - WebRTC （マイクロサービスとして機能動作）   

* 画像から人の検知で任意のイベントを動作させる機能（マイクロサービスとして機能動作）  

* （声優の）音声をイベントドリブンでストリーミングする機能（マイクロサービスとして機能動作）    

* （声優の）音声をランダムに定期的にストリーミングする機能（マイクロサービスとして機能動作）  

* 不要なデータを一定周期で削除してストレージの空きを作る機能（マイクロサービスとして機能動作）  

* エッジコンピューティング環境でクラウドから遮断された状況で安定動作する Kubernetes（Master Node）    

* AION-Core と メッセージングアーキテクチャ（RabbitMQ）（マイクロサービスとして機能動作）  

## omotebako-system 内 の 各 マイクロサービス の 再利用・応用利用   
omotebako-system 内 の 上記 各マイクロサービス は、それぞれ分割された機能として、他のシステムやアプリケーション等に再利用・応用利用できます。  

## omotebako-system に含まれるリソース  
omotebako-system には、以下の マイクロサービス等 のリソースが含まれます。  

・[aion-core](https://github.com/latonaio/aion-core)および関連リソース（Kubernetes Master Node、RabbitMQ、Fluentd、RedisCluster、MySQL、MongoDB、MongoExpressを含む）   
・[ui-frontend-for-omotebako](https://github.com/latonaio/ui-frontend-for-omotebako)    
・[ui-frontend-for-omotebako-mobile](https://github.com/latonaio/ui-frontend-for-omotebako-mobile)    
・[load-balancer-for-movable-devices](https://github.com/latonaio/load-balancer-for-movable-devices)   
・[authenticator](https://github.com/latonaio/authenticator)  
・ui-backend-for-omotebako  
・[calendar-module-kube](https://github.com/latonaio/calendar-module-kube)   
・[azure-face-api-identifier-kube](https://github.com/latonaio/azure-face-api-identifier-kube)     
・[register-face-to-guest-table](https://github.com/latonaio/register-face-to-guest-table-kube)     
・[azure-face-api-registrator-kube](https://github.com/latonaio/azure-face-api-registrator-kube)    
・[send-data-to-azure-iot-hub](https://github.com/latonaio/send-data-to-azure-iot-hub)    
・[site-controller-data-update-to-mysql](https://github.com/latonaio/site-controller-data-update-to-mysql)  
・[event-driven-face-existence-detection](https://github.com/latonaio/event-driven-face-existence-detection)    
・[event-driven-audio-streaming](https://github.com/latonaio/event-driven-audio-streaming)  
・[random-voice-streaming-periodic](https://github.com/latonaio/random-voice-streaming-periodic)    
・[mysql-backup](https://github.com/latonaio/mysql-backup)      
・[golang-logging-library](https://github.com/latonaio/golang-logging-library)   
・[python-logging-library](https://github.com/latonaio/python-logging-library)   
・[fluentd-for-containers-mongodb-kube](https://github.com/latonaio/fluentd-for-containers-mongodb-kube)  
・[data-sweeper-kube](https://github.com/latonaio/data-sweeper-kube)  