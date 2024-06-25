**SQL構文基礎**

インストールでのエラー解決法
2024.06/25 更新

エラー詳細  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

The pgAdmin 4 server could not be contacted: pgAdmin Runtime Environment
Python Path: "C:\Program Files\pgAdmin 4\v7\python\python.exe"
Runtime Config File： "ClUsers／{ユーザー名}AppDatalRoaminglpgadminVruntime_config.json"
pgAdmin Config File: "C:\Program Files\pgAdmin 4\v7\web|config.py"
Webapp Path: "C:\Program Files\pgAdmin 4\v7\web\pgAdmin4.py"
PgAdmin Command: "C:\Program Files\pgAdmin 4\v7\python\python.exe -s C:\Program Files\pgAdmin
4\v7/web|pgAdmin4.py"
Environment:
- ALLUSERSPROFILE: C:\ProgramData
-APPDATA:C:/Users/{ユーザー名}\AppDatalRoaming
- CHROME_CRASHPAD_PIPE_NAME: 11.|pipe\crashpad_20552_PUXJXYGJQIKKYCUV
-CHROME RESTART:NW.js！エラー：Nw.jsで問題が発生しました。今すぐ再起動しますか？ILEFT_TO_RIGHT
- CommonProgramFiles: C:\Program Files\Common Files  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

上記エラー内容の場合
pgAdmin 4のサーバーに接続できないというエラーメッセージが表示されています。以下の手順で問題を解決できるか確認してください。  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

**1.サービスの管理画面を開く:**
・Win + Rキーを押して「ファイル名を指定して実行」を開きます。
・「services.msc」と入力して「OK」をクリックします。  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

**2.pgAdminサービスの確認:**
・「サービス」ウィンドウで、pgAdminまたは類似の名前のサービスを探します。
・サービスが「実行中」になっているか確認します。停止している場合は、右クリックして「開始」を選択します。
・サービスが実行中の場合でも、再起動してみてください。右クリックして「再起動」を選択します。  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

**3. pgAdminデータベースファイルのバックアップと削除**
・ファイルエクスプローラーを開く:
C:\Users\[ユーザー名]\AppData\Roaming\pgAdminフォルダーに移動します。  

・データベースファイルのバックアップ:
pgadmin4.dbファイルを見つけ、別の場所（例えばデスクトップ）にコピーしてバックアップを取ります。  

・データベースファイルの削除:
pgadmin4.dbファイルを削除します。  

※バックアップの取り方
コマンドプロンプト例：
copy "C:\Users\{ユーザー名}\AppData\Roaming\pgAdmin\pgadmin4.db" "C:\Users\{ユーザー名}\Desktop\pgadmin4.db.bak"  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

**4. pgAdminの再起動**
pgAdminを再起動し、データベースが自動的に再生成されるか確認します。  
＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿＿

今回の場合pgAdminにあるデータログを全て削除して再起動する方法になります。
最初インストールする際に
PostgreSQLやpgAdminをインストールすると起きるエラーになります。  
DBが中途半端に上書きされた状態で起きています。
