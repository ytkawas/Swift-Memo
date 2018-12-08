# RxSwiftの備忘録

## 超基本
- Observableは購読される側
  - データの生成、Observerへの通知を行う
- Observerは購読(subscribe)する側
  - Observableが生成するデータのシーケンスを購読する
- オペレータ(map,flatMap,filterなど)
  - Observableのデータストリームに処理を行って新しいObservableを生成する

## 実際に触ってみる
- まずはArrayやMapをObservableしてみよう
  - toObservable()メソッドを使えばObservable化できる

~~~
// あとで書く
~~~

- 次にObservable化したデータストリームを購読してみよう
  - subscribe()メソッド、もしくはbind()メソッドを使う
    - 引数：onNext、onError、onCompleted、onDisposed,通知を受けとるObserverなど複数ある
    - 戻り値：Subscription
  - SubscriptionはObserverの登録を解除(unSubscribe)するために使う


~~~
// あとで書く
~~~

- 最後にストリームを終了しよう
  - DisposeBagにaddDisposableTo()する

~~~
// あとで書く
~~~

続く

# Getting Startedで学んだ内容


## Observables aka Sequences
- 「Observable sequence」は「sequence」にすぎない。違いは非同期でelementsを受け取ることができるかどうか。
  - Observable(ObservableType) は Sequenceと等価
  - ObservableType.subscribeメソッド は　Sequence.makeIteratorメソッドと等価
  - Sequenceの要素を受け取るために、Observer (callback)は返されたイテレータのnext()の代わりに、ObservableType.subscribeメソッドを必要とする。
- Sequencesの特徴
  - 0以上のelementを持つことができる
  - 一度でも「error」もしくは「completed」イベントを受け取ったら、新しくelementを生成しない

## 参考
- ReactiveX/RxSwift
 https://github.com/ReactiveX/RxSwift/blob/master/Documentation/GettingStarted.md
- RxJSの基本をまとめてみた~基本的な概念編(Observable、Observer、Subscriptionなど)~
 https://qiita.com/Sekky0905/items/93bd4804a2003ed0aa8d
- RxSwift の Observable とは何か
 https://qiita.com/gomi_ningen/items/c796c08fe672610beecf
- RxSwiftに取り組み始めた
 https://qiita.com/hkato193/items/b95729d48d4e223aecc8
