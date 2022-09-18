# create_local_DB_react-native

下記のサイトをもとにDBを作成する。BG6App用に作成したい。</br>
https://dev-yakuza.posstree.com/react-native/react-native-sqlite-storage/

1、準備
sqliteツールのダウンロード　　
https://sqlitebrowser.org/dl/

2、DB作成
ツールを開き、local_DBのフォルダ（リモートリポジトリはここ）にtextDBという名前でテスト用のデータベースを作成。　　
testというモデルを作成。id,name,age,emailというカラム作成。　　
この時のNNなどのバリデーション設定は、railsの時のモデル作成の制限の時と同じ。

3、検証
『SQL実行』というタブ内で下記を記述・実行してダミーデータを追加。　　

INSERT INTO　　
	test　　
	(name, age, email)　　
VALUES　　
	("aaa",  20, "aaa@aaa.aaa"),　　
	("bbb",  25, "bbb@bbb.bbb"),　　
	("ccc",  30, "ccc@ccc.ccc")　　
  
  次に　　
  
  SELECT * FROM test　　
  
 を記述・実行する。結果、下記のデータが追加されていた。成功。　　
 
id name age email　　
1	 aaa	20	aaa@aaa.aaa　　
2	 bbb	25	bbb@bbb.bbb　　
3	 ccc	30	ccc@ccc.ccc　　

4、react-nativeで利用する。　　
branchを切って作成したDBを連携してみる。　　

