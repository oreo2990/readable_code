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

最善の名前とは、誤解されない名前であり、他人が意図を正しく理解できるもの。例えば上限ならmax

