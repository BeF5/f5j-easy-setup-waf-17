シグネチャのチューニング
=========================================================

誤検知が発生した場合の対処例をご紹介します。
以下で実施する内容は、Webアプリケーションの各パラメータの役割が全て把握できている場合を除き、運用開始前から全てを設定するのは難しいかもしれません。その場合は、仮運用・本運用に入ってから、再度このチューニングを実施してください。

以下は誤検知の例です。

#. 入力内容にたまたま攻撃に関連するパラメータが含まれてしまったとします。

   .. image:: images/mod11-1.png
   |  
#. 書き込みを行うと、AWAFで攻撃として検知されてしまいます。

   .. image:: images/mo11-2.png
   |  

以降、２つの対策例をご紹介します。

誤検知したパラメータをホワイトリスト化
----------------------------------------

#. Event logで誤検知したログを確認します。

   .. image:: images/mo11-3.png
   |  
#. **Occurences** をクリックし、誤検知したパラメータ名（mtxMessage）とシグネチャID（2000028335）を確認します。

   .. image:: images/mo11-4.png
   |  
#. **Security >> Application Security : Parameters : Parameters List ** にて、:guilabel:`Create` ボタンを押します。

   .. image:: images/mo11-5.png
   |  
#. **Parameter Name** に誤検知したパラメータ名（mtxMessage）を入力し、チェックBOXをすべてクリアし、**Parameter Value Type** にて、**Ignore Value** を選択し、:guilabel:`Create` ボタンを押します。　

   .. image:: images/mo11-6.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod11-7.png
   | 
#. Windowsにて再度書き込みを行うと、書き込みが成功することを確認します。

   .. image:: images/mo11-8.png
   |  

誤検知したパラメータで該当シグネチャを無効化
--------------------------------------------

#. 今度は先程作成したParameterの **Parameter Value Type** にて、**User-Input Value** を選択し、**Attack Sigantures** タブにて、誤検知したシグネチャID（2000028335）を左に移動し、**Disabled** にし、:guilabel:`Update` ボタンを押します。　

   .. image:: images/mo11-9.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod11-10.png
   | 
#. Windowsにて再度書き込みを行うと、書き込みが成功することを確認します。

   .. image:: images/mo11-11.png
   |  