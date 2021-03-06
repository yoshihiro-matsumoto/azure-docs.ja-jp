

Apple Push Notification サービス (APNS) を介してアプリ用にプッシュ通知を登録するには、新しいプッシュ証明書、アプリケーション ID、プロジェクトのプロビジョニング プロファイルを Apple の開発者ポータルで作成する必要があります。 アプリ ID には、アプリでプッシュ通知を送受信できるようにする構成設定が含まれます。 この設定には、プッシュ通知を送受信する際に Apple Push Notification Service (APNS) による認証で必要になるプッシュ通知証明書などがあります。 これらの概念の詳細については、 [Apple Push Notification サービス](http://go.microsoft.com/fwlink/p/?LinkId=272584) の公式ドキュメントを参照してください。

#### <a name="generate-the-certificate-signing-request-file-for-the-push-certificate"></a>プッシュ証明書用に証明書の署名要求ファイルを生成する
次の手順では、証明書の署名要求の作成手順について説明します。 これは、APNS で使用するプッシュ通知証明書の生成に使用されます。

1. Mac で、キーチェーン アクセス ツールを実行します。 これは、Launchpad の **[Utilities]** フォルダーまたは **[Other]** フォルダーから開くことができます。
2. **[Keychain Access]** をクリックし、**[Certificate Assistant]** を展開して、**[Request a Certificate from a Certificate Authority]** をクリックします。
   
      ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-request-cert-from-ca.png)
3. **[User Email Address]** と **[Common Name]** を選択し、**[Saved to disk]** が選択されていることを確認して、**[Continue]** をクリックします。 必要ではないため、" **CA 電子メール アドレス** " フィールドを空白のままにします。
   
      ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-csr-info.png)
4. **[Save As]** に証明書署名要求 (CSR) ファイルの名前を入力し、**[Where]** で保存場所を選択して **[Save]** をクリックします。
   
      ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-save-csr.png)
   
      指定選択した場所に CSR ファイルが保存されます。既定の場所は [Desktop] です。 このファイル用に選択した場所を忘れないでください。

#### <a name="register-your-app-for-push-notifications"></a>アプリケーションをプッシュ通知に登録する
Apple でアプリケーション用の新しいの明示的なアプリケーション ID を作成し、さらにそれをプッシュ通知用に構成します。  

1. Apple Developer センターで [iOS Provisioning Portal](http://go.microsoft.com/fwlink/p/?LinkId=272456) に移動し、Apple ID でログインして、**[Identifiers (識別子)]** をクリックし、**[App IDs (アプリ ID)]** をクリックします。最後に、**[+]** 記号をクリックして新しいアプリを登録します。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-ios-appids.png)
2. 新しいアプリの次の&3; つのフィールドを更新し、 **[Continue]**をクリックします。
   
   * **Name**: **[App ID Description]** セクションの **[Name]** フィールドに、アプリのわかりやすい名前を入力します。
   * **Bundle Identifier**: **[Explicit App ID]** セクションに、[アプリ ディストリビューション ガイド](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/AppDistributionGuide/ConfiguringYourApp/ConfiguringYourApp.html#//apple_ref/doc/uid/TP40012582-CH28-SW8)で説明したように `<Organization Identifier>.<Product Name>` の形式で**バンドル ID** を入力します。 これは、アプリの XCode、Xamarin、または Cordova プロジェクトで使用されているものとも一致する必要があります。
   * **[Push Notifications (プッシュ通知)]**: **[App Services (アプリ サービス)]** セクションの **[Push Notifications (プッシュ通知)]** オプションを選択します。
     
     ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-new-appid-info.png)
3. [Confirm your App ID (アプリ ID の確認)] 画面で設定を確認し、正しいことを確認したら **[Register (登録)]** をクリックします。
4. 新しいアプリ ID を送信すると、**[Registration complete (登録完了)]** 画面が表示されます。 **[Done]**をクリックします。
5. Developer センターで、アプリケーション ID の一覧から作成したアプリケーション ID を見つけ、その行をクリックします。 アプリ ID の行をクリックすると、アプリの詳細が表示されます。 画面の下部にある **[Edit]** をクリックします。
6. 画面の下部までスクロールし、**[Development Push SSL Certificate]** セクションの **[Create Certificate]** ボタンをクリックします。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-appid-create-cert.png)
   
       This displays the "Add iOS Certificate" assistant.
   
   > [!NOTE]
   > このチュートリアルでは開発証明書を使用します。 運用証明書の場合も同じ処理を行います。 通知の送信と同じ証明書の種類を使用するようにします。
   > 
   > 
7. **[Choose File]**をクリックして、プッシュ証明書用に CSR を保存した場所に移動します。 次いで、 **[Generate]**をクリックします。
   
      ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-appid-cert-choose-csr.png)
8. ポータルで証明書が作成されたら **[Download]** ボタンをクリックします。
   
      ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-appid-download-cert.png)
   
       This downloads the signing certificate and saves it to your computer in your Downloads folder.
   
      ![](./media/notification-hubs-enable-apple-push-notifications/notification-hubs-cert-downloaded.png)
   
   > [!NOTE]
   > 既定では、ダウンロードした開発証明書ファイルの名前は **aps_development.cer** になっています。
   > 
   > 
9. ダウンロードしたプッシュ証明書 **aps_development.cer** をダブルクリックします。 下図のように、新しい証明書が Keychain にインストールされます。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-cert-in-keychain.png)
   
   > [!NOTE]
   > 証明書の名前は異なることがありますが、名前の前に **Apple Development iOS Push Services:** が付きます。
   > 
   > 
10. キーチェーン アクセスの **[Certificates (証明書)]** カテゴリで、作成したばかりの新しいプッシュ証明書を Ctrl キーを押しながらクリックします。 **[Export]** をクリックし、ファイルに名前を付けて、**.p12** 形式を選択します。次に、**[Save]** をクリックします。
    
    エクスポートした .p12 証明書のファイル名と場所を記録します。 これは、Azure クラシック ポータルにアップロードして APNS による認証を有効にするために使用されます。 **.p12** 形式のオプションが利用できない場合には、キーチェーン アクセス ツールの再起動が必要になることがあります。

#### <a name="create-a-provisioning-profile-for-the-app"></a>アプリケーションのプロビジョニング プロファイルを作成する
1. <a href="http://go.microsoft.com/fwlink/p/?LinkId=272456" target="_blank">iOS Provisioning Portal</a> に戻って **[Provisioning Profiles]** を選択し、**[All]** を選択してから **+** ボタンをクリックして、新しいプロファイルを作成します。 これにより、**Add iOS Provisiong Profile** ウィザードが起動します。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-new-provisioning-profile.png)
2. **[Development (開発)]** でプロビジョニング プロファイルの種類として **[iOS App Development (iOS アプリ開発)]** を選択し、**[Continue (続行)]** をクリックします。
3. 次に、**[App ID (アプリ ID)]** ドロップダウン リストから作成したばかりのアプリ ID を選択し、**[Continue (続行)]** をクリックします。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-select-appid-for-provisioning.png)
4. **[Select certificates (証明書の選択)]** 画面で、コードの署名に使用される開発証明書を選択して、**[Continue (続行)]** をクリックします。 これは署名証明書で作成したプッシュの証明書ではありません。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-provisioning-select-cert.png)
       
5. 次に、テストに使用する**デバイス**を選択し、**[Continue]** をクリックします
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-provisioning-select-devices.png)
6. 最後に、**[Profile Name]** でプロファイルの名前を選択し、**[Generate]** をクリックします。
   
       ![](./media/notification-hubs-xamarin-enable-apple-push-notifications/notification-hubs-provisioning-name-profile.png)

