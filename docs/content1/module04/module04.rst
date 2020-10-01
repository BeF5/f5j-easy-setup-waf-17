（脆弱な）WEBサーバの登録
=========================================================

#. Virtual Serverを作成します。**Local Traffic >> Virtual Servers : Virtual Server List** にて、:guilabel:`Create` ボタンを押します。

   .. image:: images/mod4-1.png
   |  
#. **Name** に任意の名称を記述し、**Destination Address/Mask** に **10.1.10.180**、**Service Port**　に **80** を設定し、**HTTP Profile (Client)** にて **HTTP** を選択、**SSL Pofile(Client)** にて **clientssl** を選択します。
   
   .. image:: images/mod4-2.png
   |    
#. **Source Address Translation** にて、**Automap** を選択します。
   
   .. image:: images/mod4-3.png
   |  
#. **Default Pool** にて、:guilabel:`+` ボタンを選択します。
   
   .. image:: images/mod4-4.png
   |  
#. Poolを作成します。**Name** にて、任意の名称を入力し、**Health Monitors** にてここでは **gateway_icmp** を選択し、New Membersに、WEBサーバ（**Address** : **10.1.20.202**, **Service Port** : **80** ）を加えて :guilabel:`Add` ボタンを押し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-5.png
   |  
#. **Default Pool** にPoolが追加されたことを確認し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-6.png
   | 
#. Windowsクライアントを起動し、https://10.1.10.180/DVWA/login.php にアクセスします。Username:admin、Password:password でログインします。
   
   .. image:: images/mod4-7.png
   | 
#. **DVWA Security** にアクセスし、**Security Level** を **Low** に設定します。
   
   .. image:: images/mod4-8.png
   | 
#. **SQL Injection** にアクセスし、**User ID** に **1' or 'a' = 'a** と入力し、SQLインジェクション攻撃をします。
   
   .. image:: images/mod4-9.png
   | 
#. User IDが複数表示されることを確認します。
   
   .. image:: images/mod4-10.png
   | 



