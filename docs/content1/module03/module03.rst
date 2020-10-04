初期設定（プロビジョニング、ネットワークの設定等）
=========================================================

#. 初期パスワード（Username:admin, Password:admin）でログインし、F5ハンズオントレーニングではパスワードを（ilovef5）に変更します。

   .. image:: images/mod3-1.png
      :scale: 60%
      :align: center
   |  
#. パスワード変更に成功したら、変更後のパスワード（Username:admin, Password:ilovef5）でログインします。
   
   .. image:: images/mod3-2.png
      :scale: 60%
      :align: center
   |       
#. :guilabel:`Next` ボタンを選択します。
   
   .. image:: images/mod3-3.png
   |  
#. ライセンスアクティベーションを行います。ライセンス投入済みの場合は、:guilabel:`Next` ボタンを選択します。
   
   .. image:: images/mod3-4.png
   |  
#. プロビジョニングを行います。**Application Security(ASM)** のみを選択し、:guilabel:`Next` ボタンを選択します。
   
   .. image:: images/mod3-5.png
   |  
#. プロビジョニングには少し時間がかかります。終了したら、:guilabel:`Continue` ボタンを選択します。
   
   .. image:: images/mod3-6.png
   |  
#. デバイス証明書の確認をし、:guilabel:`Next` ボタンを選択します。
   
   .. image:: images/mod3-7.png
   |  
#. **Host Name** に、**big80.f5jp.local** と設定し、**Time Zone** に **Japan** を選択し、**Root Account** のパスワードに **ilovef5** と記入し、:guilabel:`Next` ボタンを選択します。（F5ハンズオントレーニング以外の場合は、それぞれの環境にあった内容を設定して下さい。）
  
   .. image:: images/mod3-8.png
   |  
#. :guilabel:`Finished` ボタンを選択します。
   
   .. image:: images/mod3-9.png
   | 
#. External VLANの設定を行います。**Network >> VLANs : VLAN List** にて、:guilabel:`Create` ボタンを選択します。**Name** に **external** と設定し、**Interface** に **1.1(Untagged)** を選択し、:guilabel:`Finished` ボタンを選択します。
   
   .. image:: images/mod3-10.png
   | 
#. Internal VLANの設定を行います。**Network >> VLANs : VLAN List** にて、:guilabel:`Create` ボタンを選択します。**Name** に **internal** と設定し、**Interface** に **1.2(Untagged)** を選択し、:guilabel:`Finished` ボタンを選択します。
   
   .. image:: images/mod3-11.png
   | 
#. 以下のようになります。
   
   .. image:: images/mod3-12.png
   | 
#. External SelfIPの設定を行います。**Network >> Self IP List** にて、:guilabel:`Create` ボタンを選択します。**Name** に **external-selfip** と設定し、**IP Address** に **10.1.10.80** 、**Netmask** に **255.255.255.０** 、**VLAN/Tunnel** に **external** を選択し、**Port Locakdown** に **Allow None** を選択し、:guilabel:`Finished` ボタンを選択します。
   
   .. image:: images/mod3-13.png
   | 
#. Internal SelfIPの設定を行います。**Network >> Self IP List** にて、:guilabel:`Create` ボタンを選択します。**Name** に **internal-selfip** と設定し、**IP Address** に **10.1.20.80** 、**Netmask** に **255.255.255.０** 、**VLAN/Tunnel** に **internal** を選択し、**Port Locakdown** に **Allow Default** を選択し、:guilabel:`Finished` ボタンを選択します。
   
   .. image:: images/mod3-14.png
   | 
#. 以下のようになります。
   
   .. image:: images/mod3-15.png
   | 
#. Default Gatewayの設定を行います。**Network >> Routes** にて、:guilabel:`Create` ボタンを選択します。**Name** に任意の名前を設定し、**Destination** , **Netmask** に **0.0.0.0** を設定し、**Gateway Address** に **10.1.10.1** を設定し、:guilabel:`Finished` ボタンを選択します。

   .. image:: images/mod3-16.png
   |  
#. WEBサーバへのルーティング設定を行います。（F5ハンズオントレーニングでは、SelfIPと同じセグメントなため不要です。）

   .. image:: images/mod3-17.png
   |  
#. 以下のようになります。
   
   .. image:: images/mod3-18.png
   | 
#. DNSの設定を行います。（F5ハンズオントレーニングでは予め設定されています。）
   
   .. image:: images/mod3-19.png
   | 
#. NTPの設定を行います。**System >> Configuration : Device : NTP** にて、NTPを設定し、:guilabel:`Update` ボタンを選択します。 F5ハンズオントレーニングではNTPを利用します。
   
   .. image:: images/mod3-20.png
   | 