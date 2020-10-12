Blockingモード画面のメッセージカスタマイズ
======================================

攻撃をブロックした際にユーザに返されるレスポンスページの内容を変更することが可能です。（必須ではありません。）

#. **Security >> Application Security : Security Policies : Policies List >> ポリシー名** において、 **Response and Blocking Pages** を選択すると以下が表示されます。
   
   .. image:: images/mod17-1.png
   | 
#. **Response Body** タブにて、**Custome Response** を選択します。

   .. image:: images/mod17-2.png
   | 
#. **Response Body** において、表示させたいメッセージに変更します。

   .. image:: images/mod17-3.png
   | 
#. 右上の枠のようなボタンを押します。

   .. image:: images/mod17-4.png
   | 
#. ブロックページのレビューが表示されます。

   .. image:: images/mod17-5.png
   | 
#. メッセージが表示させたい内容と一致していれば、:guilabel:`save` を押します。

   .. image:: images/mod17-6.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod17-7.png
   | 
#. Windows Clientにて、再度SQLインジェクション攻撃を行います。ブロックメッセージが変更されていることを確認します。

   .. image:: images/mod17-8.png
   | 