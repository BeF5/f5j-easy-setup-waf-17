APMの追加設定
========================================

#. 1章のAPM設定に更に追加していきます。**RADIUS Auth** と **Advanced Resource Assign** の間の :guilabel:`+` ボタンをクリックします。

   .. image:: images/mod2-1.png
   |  
#. **Variable Assign** を選択し、:guilabel:`Add Item` を押します。
   
   .. image:: images/mod2-2.png
   |  
#. **Add new entry** を押します。
   
   .. image:: images/mod2-3.png
   |  
#. **change** を押します。
   
   .. image:: images/mod2-4.png
   |  
#. 左右それぞれに以下のように入力し、:guilabel:`Finished` ボタンを押します。
    左： **session.logon.last.department**
    右： **mcget -decode {session.radius.last.attr.<Attribute名>}**

   .. image:: images/mod2-5.png
   |  
#. :guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod2-6.png
   |  
#. 次に、前項で作成した **Variable Assign** の右隣の :guilabel:`+` マークをクリックします。
   
   .. image:: images/mod2-7.png
   |  
#. **Logon Page** を選択し、:guilabel:`Add Item` を押します。
   
   .. image:: images/mod2-8.png
   |  
#. ここではデフォルト設定のまま、:guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod2-9.png
   |  
#. 次にADサーバの情報を追加します。**Access >> Authentication >> Active Directory** にて、:guilabel:`Create` ボタンを押します。 **Name** に任意の名称を追加し、**Server Connection** で **Direct** を選択し、**Domain Controller** にADサーバのIPアドレスを追加し、:guilabel:`Finished` ボタンを押します。
   
   .. image:: images/mod2-10.png
   |  
#. Visual Policy Editorの設定に戻り、**Login Page** の右隣の :guilabel:`+` マークをクリックします。
   
   .. image:: images/mod2-11.png
   |  
#. **AD Auth** を選択し、:guilabel:`Add Item` を押します。
   
   .. image:: images/mod2-12.png
   |  
#. **Type** にて設定済みのAD Serverの設定を選択し、:guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod2-13.png
   |  
#. **AD Auth** の右隣の :guilabel:`+` マークを押します。
   
   .. image:: images/mod2-14.png
   |  
#. **AD Query** を選択し、:guilabel:`Add Item` を押します。
   
   .. image:: images/mod2-15.png
   |  
#. **Type** にて設定済みのAD Serverの設定を選択します。
   
   .. image:: images/mod2-16.png
   |  
#. **Branch Rules** タブを選択し、デフォルト設定を削除します。
   
   .. image:: images/mod2-17.png
   |  
#. **Add Branch Rule** をクリックします。
   
   .. image:: images/mod2-18.png
   |  
#. 任意の名称を入力し、**change** をクリックします。
   
   .. image:: images/mod2-19.png
   |  
#. **Advanced** タブを選択し、以下のように入力し、:guilabel:`Finished` ボタンを押します。
   expr { [mcget {session.ad.last.attr.memberOf}] contains [mcget {session.logon.last.department}] }
   
   .. image:: images/mod2-20.png
   |  
#. :guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod2-21.png
   |  
#. Group毎のACLを作成します。**Access >> Access Control Lists > User-defained ACLs** にて、:guilabel:`Create` ボタンを押し、**Name** に任意の名称を入力し、:guilabel:`Create` ボタンを押します。
   
   .. image:: images/mod2-22.png
   |  
#. 作成したUser-defined ACLを選択し、適用したいAccess Control Entryを追加し、:guilabel:`Update` ボタンを押します。
   
   .. image:: images/mod2-23.png
   |  
#. ここではテストのため、内容の異なる2種類のUser-defined ACLを追加しておきます。
   
   .. image:: images/mod2-24.png
   |  
#. Visual Policy Editorの設定に戻り、**AD Query** のquery成功先の :guilabel:`+` をクリックします。（前項にて **AD Query** を追加したことで、**Advanced Resource Assign** がなくなり、Endingが **Deny** に変わっています。）
   
   .. image:: images/mod2-25.png
   |  
#. **AD Group Resource Assign** を選択し、:guilabel:`Add Item` を押します。
   
   .. image:: images/mod2-26.png
   |  
#. **Server** にて、設定済みのADサーバの設定を選択します。
   
   .. image:: images/mod2-27.png
   |  
#. **Add new entry** を押し、Groups枠をもう一つ作成します。
   
   .. image:: images/mod2-28.png
   |  
#. **New Group** に任意のAD Group名を入力し、**Add group manually** を押します。
   
   .. image:: images/mod2-29.png
   |  
#. **Static ACLs** タブにて、設定済みの一つのACLを選択します。
   
   .. image:: images/mod2-30.png
   |  
#. **Netwrok Access** タブを選択し、設定済みのNetwork Access listを選択します。
   
   .. image:: images/mod2-31.png
   |  
#. **Webtop** タブを選択し、設定済みのWebtop listを選択し、:guilabel:`Update` ボタンを押します。
   
   .. image:: images/mod2-32.png
   |  
#. 以下のようになります。
   
   .. image:: images/mod2-33.png
   |  
#. 同様にもう一つのAD group resource assignを作成し、:guilabel:`Save` ボタンを押します。
   
   .. image:: images/mod2-34.png
   |  
#. Endingを **Allow** に変更します。

   |  
#. 最終的に以下のようになります。
   
   .. image:: images/mod2-35.png
   |  
#. 最後に、Apply Access Policyを押して、ルールを反映させます。

   |  
