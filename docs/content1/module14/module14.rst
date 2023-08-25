CVE番号によるシグネチャの検索 
======================================

各シグネチャがどのCVEに対応しているか確認することが可能です。

#. **Security >> Options : Application Security : Attack Signatures : Attack Signature List** で表示された画面の フィルタマーク をクリックすると、以下のような画面が表示されます。 **ADVANCED** タブを選択し、**References** から **CVE** を選択し、CVE番号を入力して :guilabel:`Apply` ボタンを押すと、該当するシグネチャが表示されます。
   
   .. image:: images/mod14-1.png

   .. image:: images/mod14-2.png      
   | 
   上記の CVE 番号(CVE-2017-5638)は、Apache Struts2の脆弱性に対応したシグネチャ一覧であることを表示しています。Adv.WAF では、1つのCVE番号に関連したシグネチャが複数存在していることがあります。
