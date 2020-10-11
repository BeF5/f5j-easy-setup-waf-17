APMの設定
=========================================================

#. APMをプロビジョニングします。

   .. image:: images/mod4-1.png
      :scale: 80%
      :align: center
   |  
#. VLANの設定をします。（以下はシングル構成の場合のイメージ）
   
   .. image:: images/mod4-2.png
      :scale: 80%
      :align: center
   |    
#. SelfIPの設定を行います。（以下はシングル構成の場合のイメージ）
   
   .. image:: images/mod4-3.png
      :scale: 80%
      :align: center
   |  
#. デフォルトゲートウェイを設定します。
   
   .. image:: images/mod4-4.png
      :scale: 80%
      :align: center
   |  
#. DNSの設定をします。
   
   .. image:: images/mod4-5.png
      :scale: 80%
      :align: center
   |  
#. NTPの設定をします。
   
   .. image:: images/mod4-6.png
      :scale: 80%
      :align: center
   | 
#. Access Profileを作成します。**Access >> Profiles/Policies >> Access Profiles(Per-Session Policies)** にて :guilabel:`Create` ボタンを押し、Access Profileを作成します。**Name** にて任意の名称を入力し、**Profile Type** にて、**SSL-VPN** を選択し、**Customization Type** にて **Standard** を選択し、**Language** にて **Japanese** を選択し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-7.png
   | 
#. Network Access listを作成します。**Access >> Connectivity/VPN >> Network Access(VPN) >> Network Access Lists** にて、:guilabel:`Create` ボタンを押し、**Name** に任意の名称を入力し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-8.png
   | 
#. 作成したNetwork Access Listを選択します。
   
   .. image:: images/mod4-9.png
   | 
#. SSL-VPN接続後にクライアントに割り振りたいIPアドレス（Lease Pool）を設定します。**Network Settings** タブを選択し、**IPV4 Lease Pool** の右隣の **＋** ボタンを押します。
   
   .. image:: images/mod4-10.png
   | 
#. **Name** に任意の名称、**Member List** にSSL-VPN接続後にクライアントに割り振りたいIPアドレスの範囲を指定し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-11.png
   | 
#. クライアントからSSL-VPN接続させたい接続先IPアドレスの範囲（Split tunneling）を設定します。（全てSSL-VPN経由で接続させたい場合は、本設定は不要です。）**Traffic Options** にて、**Use split tunneling for traffic** を選択し、**IPV4 LAN Address Space** にて、IPアドレス範囲を指定し、:guilabel:`Update` ボタンを押します。
   
   .. image:: images/mod4-12.png
   | 
#. Connectivityプロファイルを作成します。**Access >> Connectivity/VPN >> Connectivity >> Profiles** にて、:guilabel:`Add` ボタンを押します。**Profile Name** にて、任意の名称を入力し、**Parent Profile** にて、**/Common/connectivity** を選択し、:guilabel:`OK` ボタンを押します。
   
   .. image:: images/mod4-13.png
   | 
#. Webtop listを作成します。**Access >> Webtops >> Webtop Lists** にて、**Name** にて任意の名称を入力し、**Type** にて、**Network Access** を選択し、**Customization Type** にて **Standard** を選択し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-14.png
   | 
#. RADIUSプロファイルを作成します。 **Access >> Authentication >> RADIUS** にて、:guilabel:`Create` ボタンを押します。**Name** に任意の名称を入力し、**Server Connection** にて、**User Pool** を選択肢し、**Server Pool Name** に任意の名称を入力し、**Server Addresses** にて、パスロジ社から割り当てられたRadiusサーバのアドレス、**Server Pool Monitor** にて **udp** を選択、**Secret** にて、PassLogicクラウド申込み時に申請したRadiusシークレットを設定し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-15.png
   | 
#. 7項で作成した **Access Profile** の **Editリンク** を押します。
   
   .. image:: images/mod4-16.png
   | 
#. Visual Policy Editorが表示されます。**Start** と **Deny** の間の **+** ボタンを押します。
   
   .. image:: images/mod4-17.png
   | 
#. **External Logon Page** を選択し、:guilabel:`Add Item` ボタンを押します。
   
   .. image:: images/mod4-18.png
   | 
#. **https://<テナント名>.passlogiccloud.com/<テナント名>/ui/?sso-vpn=<アプリ名称>** と入力します。アプリ名称には、PassLogicクラウド版のRADIUSで設定したものを利用します。（例：https://bef5japan.passlogiccloud.com/bef5japan/ui/?sso-vpn=APM）また、**Split domain from full Username** にて、**No** を選択し、:guilabel:`Save` ボタンを押します。

   .. image:: images/mod4-19.png
   | 
#. 次に、前項で追加した **External Logon Page** の右側の :guilabel:`+` ボタンを押します。
   
   .. image:: images/mod4-20.png
   | 
#. **RADIUS Auth** を選択し、:guilabel:`Add Item` ボタンを押します。
   
   .. image:: images/mod4-21.png
   | 
#. **AAA Server** に前項までに設定したRadiusサーバの設定を選択し、:guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod4-22.png
   | 
#. 前項で設定した **RADIUS AUTH** の右側の :guilabel:`+` ボタンを押し、**Advanced Resource Assign** を選択し、:guilabel:`Add Item` ボタンを押します。
   
   .. image:: images/mod4-23.png
   | 
#. **Add new entry** を押します。
   
   .. image:: images/mod4-24.png
   | 
#. **Add/Delete** を押します。
   
   .. image:: images/mod4-25.png
   | 
#. **Network Access** タブにて、前項までに作成した **Network Access List** を選択します。
   
   .. image:: images/mod4-26.png
   | 
#. **Webtop** タブにて、前項までに作成したWebtopを選択し、:guilabel:`Update` ボタンを押します。
   
   .. image:: images/mod4-27.png
   | 
#. :guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod4-28.png
   | 
#. **Advanced Resource Assign** の先のEnding Boxを **Deny** から **Allow** に変更します。
   
   .. image:: images/mod4-29.png
   | 
#. **Apply Access Policy** を押します。
   
   .. image:: images/mod4-30.png
   | 
#. クライアントからアクセスするVirtual Serverを作成します。**Local Traffic >> Virtual Servers >> Virtual Server List** にて、:guilabel:`Create` ボタンを押します。**Name** にて任意の名称を入力し、**Destination Address/Mask** にてVirtual ServerのIPアドレスを入力し、**Server Port** にて **443** を入力し、**HTTP Profilce(Client)** にて **http** を選択し、**SSL Profile(Client)** にて、**clientssl** を選択し、**Access Profile** にて作成済みのプロファイル、**Connectivitiy Profile** にて作成済みのプロファイルを選択し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod4-31.png
   | 