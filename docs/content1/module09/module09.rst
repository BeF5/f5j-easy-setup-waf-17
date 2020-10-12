シグネチャのステージング解除
=========================================================

#. ステージングを解除すると、Event logに攻撃として記録されます。**Security >> Application Security : Security Policies : Policies List >> DVWA_policy** にて、**Attack Signatures** を選択し、画面右上の **Enforce all Staged Signatures** を選択し、ステージングを解除します。 

   .. image:: images/mod9-1.png
   |  
#. ステージングが解除されると、**Status** が **Enforced** となります。

   .. image:: images/mod9-2.png
   | 
#. :guilabel:`Apply Policy` を押します。

   .. image:: images/mod9-3.png
   | 
#. 再度WindowsクライアントからSQLインジェクションを試みます。

   .. image:: images/mod9-4.png
   | 
#. **Security >> Event Logs : Application : Requests** にて、**Alarm Learn** でSQLインジェクションが検出されていることを確認します。

   .. image:: images/mod9-5.png
   |  


