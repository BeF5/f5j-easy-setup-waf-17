IP Intelligence（IPI）の設定 
======================================

IP Intelligence を設定することで、既知の悪意あるIPアドレスからの攻撃をBlockすることが可能です。Appliction Security処理の前段で IPアドレスの評価が行われるため、CPU 負荷高騰を和らげる効果があります。WAF と L7DDoS において IP Intelligence を利用することが可能です。（F5ハンズオンでは設定画面のみの確認となります。）

#. **Security >> Application Security : Security Policies: : Policies List** にて、対象のポリシーを選択します。

   .. image:: images/mod16-1.png
   | 
#. **IP Intelligenc** を :guilabel:`On` にします。

   .. image:: images/mod16-2.png
   |       
#. チェックしたいカテゴリのAlarmまたはBlockにチェックを入れます。その後、 :guilabel:`Save` を押します。

   .. image:: images/mod16-3.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod16-4.png
   | 

.. note::
    上記の他、L7DoS Shun と IP Intelligence を組合せることによって、IP Intelligence の IPレピュテーションDB のリストをL7DoS 対策のShun list(Auto-blacklisting)として利用が可能です。

    IP Intelligenceを利用するには、別途サブスクリプションライセンスが必要となります。