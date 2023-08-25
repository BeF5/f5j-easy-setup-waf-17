Geolocationの設定
======================================

Geolocation Enforcement の設定を行うことで、接続される予定のない国からの接続をブロックすることが可能です。（F5ハンズオンでは設定画面の確認のみとなります。）

#. **Security >> Application Security : Policy Building : Learning and Blocking Settings** の **IP Addresses/Geolocations** において、**Access from disallowed Geolocation** の Learn/Alarm/Block がチェックされていることを確認します。
   
   .. image:: images/mod15-1.png
   | 
#. **Security >> Application Security : Security Policies: : Policies List** にて、対象のポリシーを選択します。

   .. image:: images/mod15-2.png
   | 

#. **General Setting** の **Geolocation Enforcement **  にて、接続する予定のない国を **Disallow Access** に移動し、:guilabel:`Save` を押します。

   .. image:: images/mod15-3.png
   |    
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod15-4.png
   | 