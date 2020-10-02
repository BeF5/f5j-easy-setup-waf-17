ステージングログの設定
=========================================================

ステージングのログをEvent Logs に出力するための設定を行います。（必須ではありませんが、ステージング運用される場合には便利です。）

#. **Security >> Event Logs : Logging Profiles** にて、:guilabel:`Create` ボタンを押します。任意の名前を設定し、**Application Security** のところで、**Enabled** をチェックし、**Request type** にて、**Illegal requests, and requests that include staged attack signatures** を選択し、:guilabel:`Create` ボタンを押します。

   .. image:: images/mod7-1.png
   |  
#. **Security >> Overview : Summary** にて、作成済みのVirtul Serverを選択し、一旦、Attacheした **Logging Profile(s)** をはずします。

   .. image:: images/mod7-2.png
   |  
#. 再度アタッチの設定をします。

   .. image:: images/mod7-3.png
   | 
#. 作成済みの **Logging Profile(s)** をアタッチします。

   .. image:: images/mod7-4.png
   |  
