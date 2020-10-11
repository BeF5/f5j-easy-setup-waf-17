APMとPassLogicクラウド基本連携設定イメージ
======================================

APMとPassLogicクラウド版の連携の流れは以下の通りです。

.. figure:: images/mod1-1.png
   :scale: 80%
   :align: center


#. APMにブラウザまたはEdge Clientから接続
#. PassLogicクラウド版のトークンレス認証画面にリダイレクトされる
#. ユーザIDを入力し、マス目パターンのワンタイムパスワードを入力する
#. ワンタイムパスワードを送る
#. APMに再度リダイレクトされる（ID＆ワンタイムパスワードを送る）
#. APMからPassLogicクラウド版にRADIUS認証接続する
#. 認証が確認できたら、SSL-VPN接続を許可する

