# リーダブルコード

### 第二章　名前に詰め込むべき情報

1. 明確な単語を選ぶ

    > 例えば、Getではなく、状況に応じてFetchやDownloadなどを使う。

2. 汎用的な名前をできれば避ける(tmpやretval等)

3. 具体的な名前を使って、物語を詳細に説明する

    >例えば、ServerCanStart()よりもCanListenOnPort（）のほうが明確だ。

4. 変数名に大切な情報を追加する

    >単位がつけるべき場合は、例えば、ミリ秒を表す変数名には後ろに_msをつける、またこれからエスケープが必要な変数名には、前にraw_をつける。

5. スコープの大きな変数には長い名前をつける

    >スコープが数画面に及ぶ変数には1~2文字の短い暗号めいた名前をつけてはいけない。短い名前はスコープが数行の変数につけるべきだ。

6. 大文字やアンダースコアなどに意味を含める

    >例えば、HTMLのidにはアンダースコア、　classにはハイフン。また、クラスのメンバー変数にはアンダースコア、ローカル変数にはハイフン。

### 第三章　誤解されない名前

最善の名前とは、誤解されない名前であり、他人が意図を正しく理解できるもの。例えば上下の限界値であればhmax_/min_、包括的範囲であればfirst/last、包含/排他的範囲であればbegin/endを使う。get()やsiza()には、軽量メソッドが期待されるので、あまり使わない(getが入ってる関数が重い場合、イメージと合わない)。

### 第四章　美しさ

一貫性と意味のあるやり方でコードを整理し、簡単にコードを読める様にする。以下は例。

1. 複数のコードブロックで同じ処理をしているなら、シルエットも同じようなものにする。
2. コードの列(左端とか)を整理すれば、概要が把握しやすくなる
3. 処理などの順番は、意味のあるものにして、常にその順番を守る。
4. 大きなブロックは空行を使って、論理的な段落に分ける。

### 第五章　コメントすべきこと

コメントの目的は、コードの意図を読み手に理解してもらうこと。
 
 1. コメントすべきではないこと
    - コードからすぐに抽出できること
    - 酷いコードを補助する補助的なコメント。この場合、補助コメントを書くのではなく、コードを修正する。 
 2. コメントすべき、自分の考え
    - なぜコードが他のやり方でなく、こうなっているのか
    - コードの欠陥を下記の様なコメントで補助する
        - TODO: 後でやる
        - FIXME: 既知の不具合があるコード
        - HACK: あまりきれいじゃない解決策
        - XXX: 危険、大きな問題がある
    - 定数の値が持つ「背景」
 3. コメントすべき、読み手への配慮
    - 読み手が「？」となる部分を予測しコメントをする
    - 平均的な読み手が驚く様な動作は文章化しておく
    - ファイルやクラスには「全体像」のコメントを書く。
    - 読み手が細部に捕われないように、コードブロックに概要コメントを記載する

### 第六章　コメントは正確で簡潔に

小さな領域にできるだけ多くの情報を詰め込んだコメントを書くコツは下記。

 1. 複数のものを指す可能性がある「それ」や「これ」などの代名詞を避ける。
 2. 関数の動作はできるだけ正確に説明する。
 3. コメントに含める入出力の実例を慎重に選ぶ
 4. コードの意図は、詳細レベルでなく、高レベルで記述する。
 5. よく分からない引数にはインラインコメントを使う。
 6. 多くの意味が込められている言葉や表現を使って、コメントを簡潔に保つ。

### 第七章　制御フローを読みやすく書く

制御フローを読みやすくする為に、下記を意識する。

 1. 比較の条件を書く場合は、変化する値を左に、より安定した値を右に配置する。
 2. if/else文のブロックは、適切に並び替える。一般的には、肯定形・単純・目立つものを先に処理する。この基準は衝突する場合があるが、衝突しなければ基準を守る。
 3. 三項演算子、do/whileループ、gotoなどは、コードが読みにくくなるので、なるべく使わない。
 4. 深いネスト避ける。早めにreturnしてあげる。こうすることでネストを削除したり、コードをクリーンにできる。また、「ガード説=(関数の上部で単純な条件を先に処理をする)」を意識する。

### 第八章　巨大な式を分割する

巨大な式を一度に理解しようとしても難しいので、小さく分解すべし。説明変数(式の値を保有する変数)を利用することが簡単な分解方法で、下記3点が説明変数の利点。

 1. 巨大な式を分解できる
 2. 簡潔な名前で式を説明することで、コードを文書化できる
 3. コードの主要な「概念」を読み手が認識しやすくなる

### 第九章　変数と読みやすさ

プログラムの変数はすぐに増えるので、いずれ追跡できなくなる。変数を減らして、できるだけ軽量にすればコードは読みやすくなる。具体的な削減方法は下記。

　1. 邪魔な変数を削除する

　結果をすぐに使って、「中間結果」の変数を削除する
    
  2. 変数のスコープをできるだけ小さくする

　変数を数行のコードからしか見えない位置に移動する
  
  3. 一度だけ書き込む変数を使う

  変数に一度だけ値を設定すれば、コードが理解しやすくなる(const等)
  
  
    
    


