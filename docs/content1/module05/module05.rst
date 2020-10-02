Guided configurationによるWAFポリシーの作成
=========================================================

#. **Security >> Guided Configuration** を開きます。Guided Configurationのバージョンを確認します。

   .. image:: images/mod5-1.png
   |  
#. `ASKF5のDownloadサイト <https://downloads.f5.com/>`__ にて、最新版のGuided Configurationをダウンロードします。（既に最新版をご利用の場合は、アップデート作業は不要なので、手順7に進んで下さい。）

   .. image:: images/mod5-2.png
   |  
#. AWAFの先程の画面に戻り、ダウンロードしたGuided Configurationファイル（xxx.tar.gz）をアップロード、インストールします。

   .. image:: images/mod5-3.png
   |  
#. インストールしている途中のイメージです。

   .. image:: images/mod5-4.png
   |  
#. インストールが終了したら、:guilabel:`Continue` ボタンを押します。

   .. image:: images/mod5-5.png
   |  
#. Guided Configurationのバージョンがアップデートされていることを確認します。

   .. image:: images/mod5-6.png
   |  
#. **Web Application Protection** の **Web Application Protection** を選択します。

   .. image:: images/mod5-7.png
   |  
#. **DNS**, **NTP**, **Routing** が設定OKとなっていることを確認し、:guilabel:`Next` ボタンを押します。

   .. image:: images/mod5-8.png
   |  
#. **Security Policy Name** に任意の名前を設定し、**Enforcement Mode** にて **Transparent** を選択し、**type of policy to protect application** にて、**Generic** を選択し、**Server Technologies** にて利用しているミドルウェアや言語を選択します。F5ハンズオン環境では、**Apache**, **MySQL**, **PHP** を選択し、:guilabel:`Next` ボタンを押します。

   .. image:: images/mod5-9.png
   |  
#. 既にVirtual Serverは作成済みなので、ここでは、**Assign Policy to Virtual Server(s)** にチェックを入れ、**Use Existing** を選択し、作成済みのVirtul Serverを右に移動させ、:guilabel:`Next＆Next` ボタンを押します。

   .. image:: images/mod5-10.png
   | 
#. 内容を確認し、:guilabel:`Deploy` ボタンを押します。

   .. image:: images/mod5-11.png
   |  
#. 作成したWAFのポリシーにLogging Profileをアタッチします。**Security >> Overview:Summary** にて、**Attach** の **Logging Profile** を選択します。

   .. image:: images/mod5-12.png
   |  
#. **Log illegal requests** を選択し、:guilabel:`Attach` ボタンを押します。

   .. image:: images/mod5-13.png
   |  
#. **Local Traffic >> Virtual Servers:Virtual Server List** にて作成済みのVirtul Serverを選択し、**Security** タブを選択します。**Application Security Policy** と　**Log Profile** がそれぞれ設定されていることを確認します。

   .. image:: images/mod5-14.png
   |  
#. ご検知対策、負荷防止対策を設定します。（必須ではありません。） **Security >> Application Security : Policy Building : Learning and Blocking Settings** を開きます。日本語サイトの誤検知の防止策として、**Failed to convert character** をOFFにします。また、**Data Guard:
Information Leakage Detected** もパフォーマンス面を考慮してOFFにし、:guilabel:`Save` ボタンを押します。

   .. image:: images/mod5-15.png
   |  
#. :guilabel:`Apply Policy` ボタンを押し、ポリシーを反映させます。

   .. image:: images/mod5-16.png
   | 
