PassLogicクラウド版の設定
=========================================================

#. パスロジ社に申請した自社のテナントの管理画面にログインします。

   .. image:: images/mod3-1.png
      :scale: 60%
      :align: center
   |  
#. 事前に設定したマス目パターンのワンタイムパスワードを入力します。
   
   .. image:: images/mod3-2.png
      :scale: 80%
      :align: center
   |       
#. **RADIUS - SSO** の設定をします。**RADIUS** の **No.** に **1** と入力し、**アプリケーション名称** に任意の名前を入力し、**認証の送信先URL** において、**https://<APMのFQDNまたはIPアドレス>/my.policy** と入力し、**ログインIDのValue属性** において **Passlogic Domain** を選択し、**テナント追加** にチェックを入れ、:guilabel:`次へ` ボタンを押します。（ここで設定する **アプリケーション名称** はAPM側の設定で利用します。）
   
   .. image:: images/mod3-3.png
   |  
#. 入力内容を確認し、決定ボタンを押します。
   
   .. image:: images/mod3-4.png
   |  
#. ドメイン名を以下のように任意の名称で作成します。（ドメイン名を作成せず、localでも接続可）
   
   .. image:: images/mod3-5.png
      :scale: 60%
      :align: center
   |  
#. ポリシーを以下のように任意の名称で作成します。 （ポリシーの設定内容はここでは省略します。Passlogicクラウド版のマニュアルをご確認下さい。）
   
   .. image:: images/mod3-6.png
      :scale: 60%
      :align: center
   |  
#. グループ名を以下のように任意の名称で作成します。（設定しなくても接続可）
   
   .. image:: images/mod3-7.png
      :scale: 60%
      :align: center
   |  
#. 認証対象ユーザを作成します。**uid** を入力し、**ドメイン名** 、**ポリシー** 、**グループ１** は前項までに作成したものを選択します。その他必要事項を入力し、ワンタイムパスワード用のマス目パターンを入力し、次へボタンを押します。
  
   .. image:: images/mod3-8.png
   |  
#. **attribute1** にADのグループ名を入力します。（こちらの値は、２章のAD認証との組合せによる設定例において利用します。本設定は必須ではございません。）注意：attributeを利用したい場合は、事前にパスロジ社に申請し、attribute名を登録して頂く必要がございます。
   
   .. image:: images/mod3-9.png
   | 
#. ここではテストのため、別のポリシー、グループを持つ他のユーザを登録しておきます。
   
   .. image:: images/mod3-10.png
      :scale: 60%
      :align: center
   | 
#. 属性も異なる値を登録しておきます。
   
   .. image:: images/mod3-11.png
      :scale: 60%
      :align: center
   | 
