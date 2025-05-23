## 概要

ROS2開発における操作の煩雑さの低減を目的としたCLIツールを作成しました．
本ツールは１つのターミナルで完結するように作られており，主な機能には下記のようなものが挙げられます．

- ノードの起動・停止
- ライフサイクルノードの遷移
- ノードのログの表示
- トピック表示およびパブリッシュ

本ツールにより複数のターミナルを立ち上げる必要がなくなるため，目的のターミナルを探す手間が省け，システム開発環境をシンプルに保つことができるようになります．



## 背景と目的

ROSの開発では，ノードの起動方法に`ros2 run`と`ros2 launch`という２つの方法がありますが，それぞれ下記のような問題がありました．

- `ros2 run`
  - 欠点：ノードの数が増えるに従いターミナルの数も増加します．その結果，目的のノードが立ち上がっているターミナルを見つけるために，あちこちのターミナルを確認する必要があります．
  - 利点：`ros2 launch`と異なり，１つのターミナルで表示されるログは基本的に１つのノードであるため，ログの確認が容易です．
- `ros2 launch`
  - 欠点：複数のノードのログが１つのターミナル上に混在することになり，エラーが発生したときの確認が難しくなります．
  - 利点：１つのターミナルに情報が集約されるため，目的のノードが起動しているターミナルを探す必要がありません．

以前にも似たようなツールは存在しました．それらは情報の表示にとどまっており，ノードの起動やライフサイクルノードの遷移を行う機能を有するものはありませんでした．本ツールは情報の集約のみならずノードの管理も行うことにより，より快適なROS開発生活をエンジョイすることに寄与します．



## CLIツールの機能

### 画面説明



![image_topview](https://github.com/harumo11/roscon_jp_2025/blob/main/topview.png?raw=ture) 

![image_topic_echo](https://github.com/harumo11/roscon_jp_2025/blob/main/topic_echo.png?raw=true)





## まとめ

- ROS開発における画面の煩雑さを減らし，シンプルに保つことによって，デバッグ効率を上げるためにツールを開発した
- １つのターミナルに全情報を集約し，またシステムのデバッグ中に頻発するであろうノードの操作も統合した．
- 本ツールを使用することでROS2システムのデバッグ効率が上がり，より品質の高いシステムが作れることを期待している