#### Omotesando.rb #60

- - -

## 最近の irb 事情

---

#### 自己紹介
- - -

* 名前：osyo
* Twitter : [@pink_bangbi](https://twitter.com/pink_bangbi)
* github  : [osyo-manga](https://github.com/osyo-manga)
* ブログ  : [Secret Garden(Instrumental)](http://secret-garden.hatenablog.com)
* 趣味で Ruby にパッチを投げたり気になった bugs.ruby のチケットをブログにまとめたりしている                     <!-- .element: class="fragment" -->
* Kaigi on Rails                 <!-- .element: class="fragment" -->
    * [ActiveRecord の歩み方](https://speakerdeck.com/osyo/activerecord-falsebu-mifang)
* 銀座Rails                   <!-- .element: class="fragment" -->
    * [これからの Ruby と今の Ruby について](https://speakerdeck.com/osyo/korekarafalse-ruby-tojin-false-ruby-nituite)
    * [12月25日にリリースされる Ruby 3.0 に備えよう！](https://speakerdeck.com/osyo/12yue-25ri-niririsusareru-ruby-3-dot-0-nibei-eyou)
* BuriKaigi2021                 <!-- .element: class="fragment" -->
    * [Ruby 2.0 から Ruby 3.0 を駆け足で振り返る](https://speakerdeck.com/osyo/ruby-2-dot-0-kara-ruby-3-dot-0-woqu-kezu-dezhen-rifan-ru)

---

## 今日話すこと
## 最近の irb 事情

---

#### Ruby 2.7
- - -

* Ruby 2.7 以前では GNU Readline で対話環境を実装していた      <!-- .element: class="fragment" -->
    * GNU Readline とはテキスト入力を支援する為の汎用ライブラリ
        * カーソル移動やヒストリ補完などの機能が実装されている
        * emacs mode や vi mode なども実装されている
    * Ruby の標準にもこれをラップした [readline ライブラリ](https://docs.ruby-lang.org/ja/latest/library/readline.html)がある
* Ruby 2.7 では GNU Readline をピュア Ruby で実装した reline というライブラリが開発され irb はそれを利用するように改良された      <!-- .element: class="fragment" -->
    * readline の機能が GNU Readline に依存することなく使用できる
* これにより Ruby 2.7 以降では以下のような機能が irb で利用できるようになった        <!-- .element: class="fragment" -->
    * 複数行編集機能
    * シンタックスハイライト
    * 簡単なコード補完
    * リファレンスの参照機能

---

#### Ruby 3.0
- - -

* 長いテキストを貼り付けた際のパフォーマンスが改善された       <!-- .element: class="fragment" -->
    * 関連：https://github.com/ruby/irb/issues/43
* measure 機能が追加された        <!-- .element: class="fragment" -->
    * irb 上で measure メソッドを実行するとそれ以降の実行時間も出力されるようになる
        * measure :off でオフになる
    * gem install stackprof すると measure :stackprof でメソッドのプロファイリングも行われる
    * 参照：[IRB’s Built-in Measure | Jemma Issroff](https://jemma.dev/blog/irb-measure)

---

## デモ

---

#### 弊害
- - -

* irb / reline は Ruby で実装されている       <!-- .element: class="fragment" -->
* なので irb 上で Ruby のメソッドを変更するとそれが irb / reline にも反映される       <!-- .element: class="fragment" -->
* 例えば irb 上で def method = nil みたいに method メソッドを定義するとクラッシュする      <!-- .element: class="fragment" -->

---

#### まとめ
- - -

# irb すごい      <!-- .element: class="fragment" -->

---

#### 参照
- - -

* [The Hidden Gems of Ruby's IRB](https://technology.doximity.com/articles/the-hidden-gems-of-ruby-s-irb)
* [IRB’s Built-in Measure | Jemma Issroff](https://jemma.dev/blog/irb-measure) 

---


### ご清聴
### ありがとうございました

