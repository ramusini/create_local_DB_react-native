# BG6AppのDBをFireStoreではなく、ローカルで作成する

下記のサイトをもとにDBを作成する。BG6App用に作成したい。</br>
https://dev-yakuza.posstree.com/react-native/react-native-sqlite-storage/</br>

#1、準備</br>
sqliteツールのダウンロード　　</br>
https://sqlitebrowser.org/dl/</br>

#2、DB作成
ツールを開き、local_DBのフォルダ（リモートリポジトリはここ）にtextDBという名前でテスト用のデータベースを作成。</br>
testというモデルを作成。id,name,age,emailというカラム作成。</br>
この時のNNなどのバリデーション設定は、railsの時のモデル作成の制限の時と同じ。</br>

#3、検証
『SQL実行』というタブ内で下記を記述・実行してダミーデータを追加。</br>

INSERT INTO</br>
	test</br>　　
	(name, age, email)</br>　　
VALUES</br>
	("aaa",  20, "aaa@aaa.aaa"),</br>
	("bbb",  25, "bbb@bbb.bbb"),</br>
	("ccc",  30, "ccc@ccc.ccc")</br>

次に</br>

  SELECT * FROM test</br>

 を記述・実行する。結果、下記のデータが追加されていた。成功。</br>

id name age email</br>
1	 aaa	20	aaa@aaa.aaa</br>
2	 bbb	25	bbb@bbb.bbb</br>
3	 ccc	30	ccc@ccc.ccc</br>

#4、react-nativeで利用する。</br>
branchを切って作成したDBを連携してみる。</br>　　

#備考
* NN,PK,AI,Uの意味
	* NN=Not Null
	* PK＝Primary Key
	* Auto Increment（自動番号割り当て）
	* U=Unique（一意）

* リレーションの構築の仕方。
一対多の関係。一＝A、多＝Bの場合</br>

SELECT *</br>
FROM B</br>
  INNER JOIN A ON B.A_id = A.id;</br>

BのカラムのA_idと、Aのカラムのidが結合される。</br>
