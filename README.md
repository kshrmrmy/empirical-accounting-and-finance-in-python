# （Python版リポジトリ）笠原晃恭・村宮克彦『実証会計・ファイナンス - Rによる財務・株式データの分析』新世社，2022年

<img src="https://www.saiensu.co.jp/bookImages/2022-978-4-88384-349-7.jpg" width="180px" >

本リポジトリでは，新世社より出版されている[『実証会計・ファイナンス - Rによる財務・株式データの分析』](https://www.saiensu.co.jp/search/?isbn=978-4-88384-349-7&y=2022)に記載したRコードと一対一で対応する**Pythonコード**を配布する．コードは，Jupyter Labで動作確認を行ったipynb形式で提供し，各章ごとにファイルを分割している．


- 本リポジトリは，あくまで笠原・村宮 (2022)の付録的な位置づけであるため，各コードの詳細なフローやその説明，及び種々の関数・メソッドの使い方については最低限の解説しかしていないことを予め了承いただきたい．
- 本書の[サポートサイト](https://www2.econ.osaka-u.ac.jp/~eaafinr/)では，データやRコードの一覧，オンライン付録などを掲載している．
- Rコードの配布用GitHubリポジトリは，別途[ここ](https://github.com/kshrmrmy/empirical-accounting-and-finance-in-r)に用意している．
- 本書で使用するデータについては，[サポートサイトのS2節](https://www2.econ.osaka-u.ac.jp/~eaafinr/sect-2.html)よりダウンロード可能である．なお，データのダウンロードにあたっては，本書「まえがき」ivページ記載のパスワードを入力してほしい．
- 本リポジトリのPythonコードの作成・動作確認にあたっては，彭遠超氏（大阪大学大学院経済学研究科・D3）に支援いただいた．記して，ここに感謝の意を表したい．

## 使い方

1. 本リポジトリをクローンするか，「Code > Download ZIP」からダウンロードして展開する．
2. サポートサイトのS2節から`simulation_data.zip`をダウンロードし，パスワードを入力して展開する．`simulation_data`というフォルダの中に，`ch03_daily_stock_return.csv`などのCSVファイルが入っている．
3. 各ノートブックは，`pd.read_csv("ch03_daily_stock_return.csv")`のように**ノートブックと同じフォルダ**にあるCSVファイルを読み込む．したがって，展開した`simulation_data`フォルダの中に`ch03.ipynb`〜`ch08.ipynb`をコピーして開くのが最も簡単である（あるいは，CSVファイルをノートブックと同じフォルダに置いてもよい）．
4. 必要なライブラリは`pandas`，`numpy`，`matplotlib`，`seaborn`，`scipy`，`statsmodels`，`cvxopt`，`session_info`である．Jupyter Labとあわせて，`pip install jupyterlab pandas numpy matplotlib seaborn scipy statsmodels cvxopt session_info`でインストールできる．
5. 第5章以降のノートブックは，前章までで作成した`ch04_output.csv`などの中間データを読み込むが，これらも`simulation_data.zip`に含まれているので，途中の章から始めることもできる．

## 動作確認環境

Python 3.13.17，pandas 3.0.6，numpy 2.5.4，matplotlib 3.11.2，seaborn 0.13.2，scipy 1.18.1，statsmodels 0.15.0，cvxopt 1.3.3，JupyterLab 4.6.4（macOS 27.0.1，2026年10月）．各ノートブック末尾の`session_info`の出力も参照のこと．

## 更新履歴

- 2026年10月：全章を上記の環境で再実行し，pandas 3.0・numpy 2.x でエラーになっていた箇所（ch03_54，ch06_30，ch06_36）を修正．あわせて，本書の記述と一致していなかった箇所（ch03_10・ch03_11 の行列の並び，ch05_29 の分散の自由度，ch08_08 の残差標準誤差），空の図を保存していた箇所（ch03_09，ch03_58），計算結果が表示されていなかった箇所（ch06_24，ch06_41，ch07_09，ch08_13）を修正し，`groupby().apply()` を `agg()`／`transform()` に置き換えるなどコードを整理．本書の ch03_30，ch05_34〜36 に対応するセルを追加．
- 2024年2月：初版公開（Python 3.11，pandas 2.2）．
