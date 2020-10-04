シグネチャ、TCシグネチャのアップデート
======================================

#. シグネチャが更新された場合に、ステージングモードで運用するか、即座にLearn/Alarm/Blockの設定が適用されるかの指定が可能です。また、既存シグネチャの更新後の振る舞いについての指定も可能です。**Security >> Application Security : Policy Building : Learning and Blocking Settings** の **Attack Signatures** にて表示された画面で、必要に応じて希望する動作への設定変更を実施します。（変更する場合、Save, ApplyPolicyで反映させます。）

   .. image:: images/mod13-1.png
   
   .. note::
      Enforce updated rule immediately for non-staged signatures:
         Enforcement 状態(Non-Staging)の既存シグネチャがアップデート された場合、更新されたシグネチャも Non-Staging とします。
      Retain previous rule enforcement and place updated rule in staging:
         Enforcement 状態(Non-Staging)の既存シグネチャがアップデート された場合、更新前のシグネチャは Non-Staging のままとし、更新 されたシグネチャを Staging とします。更新されたシグネチャの Staging 期間が終了した際に、更新前の シグネチャが削除され、更新されたシグネチャが Non-Staging とな ります。

#. **System >> Software Management : Live Update** で表示された画面で、**Check for Updates** をクリックして、シグネチャ更新の有無を確認します。

   .. image:: images/mod13-2.png
   | 
#. チェック中のイメージです。(チェックには数分かかります。)

   .. image:: images/mod13-3.png
      :scale: 80%
      :align: center
   | 
#. 更新可能なシグネチャがある場合、以下のように表示されます。☓を推し、画面を閉じます。

   .. image:: images/mod13-4.png
      :scale: 60%
      :align: center
   | 
#. 全てをインスールしたい場合は、InstallAllUpdatesをクリックします。

   .. image:: images/mod13-5.png
   | 
#. シグネチャ更新中は、以下のように表示されます。(更新には数分かかります。)

   .. image:: images/mod13-6.png
      :scale: 60%
      :align: center
   | 
#. Install が完了すると以下のようになります。☓を推し、画面を閉じます。

   .. image:: images/mod13-7.png
      :scale: 60%
      :align: center
   | 
#. 以下が更新後のイメージとなります。CurrentlyInstaslledステータスのシグネチャをクリックします。

   .. image:: images/mod13-8.png
   | 
#. UpdateされたSignatureの情報が表示されます。各Entityをクリックすると、該当するシグネチャ一覧が確認できます。

   .. image:: images/mod13-9.png
      :scale: 80%
      :align: center
   | 
#. Update がない場合は Install Updates をクリックしても以下のように表示されます。

   .. image:: images/mod13-10.png
      :scale: 80%
      :align: center
   | 
#. 追加されたシグネチャがステージングになっているかどうかの確認方法を示します。**Security >> Application Security : Security Policies : Policies List >> DVWA_policy** で表示された画面で、**Status** を **Staging** でフィルタリングします。

   .. image:: images/mod13-11.png
   | 
#. 追加されたシグネチャがステージングとなっていることが分かります。

   .. image:: images/mod13-12.png
   | 

.. note::
    新しいSignatureをUpdateすることで新たな攻撃に対応することができます。Signatureの更新についての詳細は、以下の記事を参考にして下さい。
    https://support.f5.com/csp/article/K82512024

