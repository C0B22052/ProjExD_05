# ゲームのタイトル
* Pacman

## 実行環境の必要条件
* python >= 3.10
* pygame >= 2.1

## ゲームの概要
参考サイトurl:https://github.com/hbokmann/Pacman
1900年代に誕生したパックマン、画面上を動き回る敵(ゴースト)を避けながら画面上にある黄色のクッキーを食べつくすゲーム
矢印キーで操作し、クッキーをすべて食べ終えるとクリア

## ゲームの実装
### 共通基本機能
* 迷路の壁に関するクラス
* 主人公キャラクターに関するクラス
* 敵キャラクターに関するクラス
* 音楽の再生
* クッキー（Block）に関するクラス


### 担当追加機能
* 金城：スペースキーを押すとscoreを40ポイント消費して敵キャラの動きを約6秒程度停止する,class Ghostの中でkkkの値が１の場合は通常通りゴーストを動かし、０の場合はゴーストの移動リストを回らないようにしてゴーストの動きを停止する。スペースキーを押す、かつ、scoreが４０以上であればscoreを４０消費してkkkを０にする。
stop_lifeを50に設定し、startGame()で１ずつ引いていくstop_lifeが０未満になったらkkkを１にする。

* 工藤：・Tキーを押すとパックマンををランダムな位置にテレポートさせる機能。Tキーが押下されたとき、Player クラスのteleport関数を呼び出し、ランダムな位置をしていする。また、壁や扉、ゴーストとの衝突判定を行い、おかしな位置に転移しないようになっている。
　　　　・パックマンの向きを変更する機能。十字キーからパックマンの進む方向を取得し、向きを変更する。
　　　　・パックマンの口をパクパクさせる機能。ゲーム内のタイムをpygame.time.get.ticks()によって取得し、1000の剰余が500以上のときに、パックマンの口を閉じる画像に変更する。


* 佐々木: LSHIFTキーを押しながら動かすと壁をすり抜けることができる機能。動く座標は30ずつ動くようになっているので、それを60にすることによって、壁などもすり抜けることができる。そして、それだと一番外の壁もすり抜けてしまう恐れもあるので、壁の厚さを変えて通り抜けないようにした。

* 伊藤：障害物を表示する機能。Jキーを押すと対角線にGhostClassの障害物を表示する。当たるとゲームオーバーになる。ON,OFFを自由に切り替えられる。

* 金子C0A22046:　画面の一部を上から黒い画像を透過することにより隠す機能。隠すタイミングはscoreを参照していて表示する場合としない場合を１０ずつ交互に表示するようにしている。またscoreの値は隠さないように表示している。

### ToDo  実装しようと思ったけど時間が足りずできなかったことなど
- [ ] ゴーストの動き方をランダムにする機能
### メモ  グループメンバーへの連絡など
* kkkは0か1の値をとり,kkkが1の時turn(ゴーストが一度動くターン)に+1されてリストが周り次のターンに行きゴーストが次の行動を行う、kkkが0の時リストが回らずゴーストは次の行動ができなくなる。
* クッキーは座標上ではx,yともに30ごとに置かれている。
* 博打なので通り抜けはタイミングが大事。
* 敵は障害物に影響されないので注意。
