シグネチャの動作確認
=========================================================

#. Windowsクライアントを起動し、https://10.1.10.180/DVWA/login.php にアクセスします。Username: **admin**、Password: **password** でログインし、**SQL Injection** にアクセスし、**User ID** に 1' or 'a' = 'a と入力し、SQLインジェクション攻撃をします。(本ガイドからコマンドはコピーしないで下さい。シングルクォーテーションに注意してタイプして下さい。。)

   .. image:: images/mod8-1.png
   |  
#. **Security >> Event Logs : Application : Requests** にて、**Staged** でSQLインジェクションが検出されていることを確認します。

   .. image:: images/mod8-2.png
   |  
#. 上記画面のSuggestionsの **View...** をクリックすると、TrafficLearningの画面でも **Attack signature detected** が確認できます。（ **Security >> Application Security : Policy Building : Traffic Learning** でもたどれます。）

   .. image:: images/mod8-3.png
   |  



