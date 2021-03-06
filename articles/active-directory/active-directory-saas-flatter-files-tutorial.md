---
title: "チュートリアル: Azure Active Directory と Flatter Files の統合 | Microsoft Docs"
description: "Azure Active Directory と Flatter Files の間でシングル サインオンを構成する方法について説明します。"
services: active-directory
documentationcenter: 
author: jeevansd
manager: femila
editor: 
ms.assetid: f86fe5e3-0e91-40d6-869c-3df6912d27ea
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 02/10/2017
ms.author: jeedes
translationtype: Human Translation
ms.sourcegitcommit: 488a3c5f0aa05c5b71bf5d72539cbc4b7c6de1b5
ms.openlocfilehash: 062878ad877b501ce7f0d5c4f8ce9ca939ffe64d
ms.lasthandoff: 02/17/2017


---
# <a name="tutorial-azure-active-directory-integration-with-flatter-files"></a>チュートリアル: Azure Active Directory と Flatter Files の統合
このチュートリアルの目的は、Flatter Files と Azure Active Directory (Azure AD) を統合する方法を説明することです。  

Flatter Files と Azure AD の統合には、次の利点があります。 

* Flatter Files にアクセスする Azure AD ユーザーを制御できます。 
* ユーザーが自分の Azure AD アカウントで自動的に Flatter Files にシングル サインオン (SSO) できるようにします。
* 1 つの中央サイト (Azure Active Directory クラシック ポータル) でアカウントを管理できます。

SaaS アプリと Azure AD の統合の詳細については、「 [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](active-directory-appssoaccess-whatis.md)」を参照してください。

## <a name="prerequisites"></a>前提条件
Flatter Files と Azure AD の統合を構成するには、次のものが必要です。

* Azure AD サブスクリプション
* Flatter Files でのシングル サインオンが有効なサブスクリプション

>[!NOTE]
>このチュートリアルの手順をテストする場合、運用環境を使用しないことをお勧めします。 
> 

このチュートリアルの手順をテストするには、次の推奨事項に従ってください。

* 必要な場合を除き、運用環境は使用しないでください。
* Azure AD の評価環境がない場合は、 [こちら](https://azure.microsoft.com/pricing/free-trial/)から&1; か月の評価版を入手できます。 

## <a name="scenario-description"></a>シナリオの説明
このチュートリアルの目的は、テスト環境で Azure AD のシングル サインオンをテストできるようにすることです。  

このチュートリアルで説明するシナリオは、主に次の&2; つの要素で構成されています。

1. ギャラリーからの Flatter Files の追加 
2. Azure AD シングル サインオンの構成とテスト

## <a name="add-flatter-files-from-the-gallery"></a>ギャラリーからの Flatter Files の追加
Azure AD への Flatter Files の統合を構成するには、ギャラリーから管理対象 SaaS アプリの一覧に Flatter Files を追加する必要があります。

**ギャラリーから Flatter Files を追加するには、次の手順に従います。**

1. **Azure クラシック ポータル**の左側のナビゲーション ウィンドウで、**[Active Directory]** をクリックします。 
   
    ![Active Directory][1]
2. **[ディレクトリ]** の一覧から、ディレクトリ統合を有効にするディレクトリを選択します。
3. アプリケーション ビューを開くには、ディレクトリ ビューでトップ メニューの **[アプリケーション]** をクリックします。
   
    ![[アプリケーション]][2]
4. ページの下部にある **[追加]** をクリックします。
   
    ![アプリケーション][3]
5. **[実行する内容]** ダイアログで、**[ギャラリーからアプリケーションを追加します]** をクリックします。
   
    ![アプリケーション][4]
6. 検索ボックスに、「 **Flatter Files**」と入力します。

    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_01.png)

7. 結果ウィンドウで **[Flatter Files]** を選択し、**[完了]** をクリックしてアプリケーションを追加します。
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_500.png)

## <a name="configure-and-test-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成とテスト
このセクションの目的は、"Britta Simon" というテスト ユーザーに基づいて、Flatter Files で Azure AD のシングル サインオンを構成し、テストする方法について説明することです。

SSO を機能させるには、Azure AD ユーザーに対応する Flatter Files ユーザーが Azure AD で認識されている必要があります。 言い換えると、Azure AD ユーザーと Flatter Files の関連ユーザーの間で、リンク関係が確立されている必要があります。  

このリンク関係は、Azure AD の **[ユーザー名]** の値を、Flatter Files の **[Username]** の値として割り当てることで確立されます。

Flatter Files で Azure AD のシングル サインオンを構成してテストするには、次の構成要素を完了する必要があります。

1. **[Azure AD シングル サインオンの構成](#configuring-azure-ad-single-single-sign-on)** - ユーザーがこの機能を使用できるようにします。
2. **[Azure AD のテスト ユーザーの作成](#creating-an-azure-ad-test-user)** - Britta Simon で Azure AD のシングル サインオンをテストします。
3. **[Flatter Files テスト ユーザーの作成](#creating-a-halogen-software-test-user)** - Flatter Files で Britta Simon に対応するユーザーを作成し、Azure AD の Britta Simon にリンクさせます。
4. **[Azure AD テスト ユーザーの割り当て](#assigning-the-azure-ad-test-user)** - Britta Simon が Azure AD のシングル サインオンを使用できるようにします。
5. **[Testing Single Sign-On](#testing-single-sign-on)** - 構成が機能するかどうかを確認します。

### <a name="configure-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成
このセクションの目的は、Azure AD クラシック ポータルで Azure AD のシングル サインオンを有効にすることと、Flatter Files アプリケーションでシングル サインオンを構成することです。 この手順の途中で、base-64 でエンコードされた証明書ファイルを作成する必要があります。 この手順に慣れていない場合は、「 [How to convert a binary certificate into a text file (バイナリ証明書をテキスト ファイルに変換する方法)](http://youtu.be/PlgrzUZ-Y1o)」をご覧ください。
Flatter Files のシングル サインオンを構成するには、登録済みのドメインが必要です。 登録済みのドメインがない場合は、Flatter Files のサポート チーム ( [support@flatterfiles.com](mailto:support@flatterfiles.com)」を参照してください。  

**Flatter Files で Azure AD シングル サインオンを構成するには、次の手順に従います。**

1. Azure AD クラシック ポータルの **Flatter Files** アプリケーション統合ページで **[シングル サインオンの構成]** をクリックし、**[シングル サインオンの構成]** ダイアログを開きます。
   
    ![Configure Single Sign-On][6] 
2. **[ユーザーの Flatter Files へのアクセスを設定してください]** ページで、**[Microsoft Azure AD のシングル サインオン]** を選択し、**[次へ]** をクリックします。
       ![[シングル サインオンの構成]](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_02.png) 
3. **[アプリケーション設定の構成]** ページで、**[次へ]** をクリックします。
   
    ![[シングル サインオンの構成]](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_03.png) 
   >[!NOTE]
   >Flatter Files では、すべてのユーザーに同じ SSO ログイン URL ([https://www.flatterfiles.com/site/login/sso/](https://www.flatterfiles.com/site/login/sso/)) が使用されます。
   > 
   
4. **[Flatter Files でのシングル サインオンの構成]** ページで、次の手順に従います。
   
    ![[シングル サインオンの構成]](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_04.png)  
    1. **[証明書のダウンロード]** をクリックし、コンピューターにファイルを保存します。
    2. **[次へ]**をクリックします。
5. 管理者として Flatter Files アプリケーションにサインオンします。
6. [ダッシュボード] をクリックします。 
   
    ![[シングル サインオンの構成]](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_05.png)  
7. **[設定]** をクリックし、**[会社]** タブで次の手順に従います。 
   
    ![Configure Single Sign-On](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_06.png)  
    1. **[Use SAML 2.0 for Authentication]** を選択します。
    2. **[Configure SAML]** をクリックします。
8. **[SAML Configuration]** ダイアログ ボックスで、次の手順を実行します。 
   
    ![[シングル サインオンの構成]](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_08.png)  
   1. [Domain] ボックスに、登録済みのドメインを入力します。
   
    >[!NOTE]
    >登録済みのドメインがない場合は、Flatter Files のサポート チーム ([support@flatterfiles.com] (mailto:support@flatterfiles.com)) に問い合わせてください。 
    >    
   2. Azure クラシック ポータルの [Flatter Files でのシングル サインオンの構成] ダイアログでシングル サインオン サービス URL をコピーし、[Identity Provider URL] ボックスに貼り付けます。
   3.  ダウンロードした証明書から **base-64 でエンコードされた** ファイルを作成します。  
 
   >[!TIP]
   >詳細については、「 [How to convert a binary certificate into a text file (バイナリ証明書をテキスト ファイルに変換する方法)](http://youtu.be/PlgrzUZ-Y1o)」をご覧ください。
   >  
   4.  base-64 でエンコードされた証明書をメモ帳で開き、その内容をクリップボードにコピーして、**[FlatterFiles Identity Provider Certificate]** ボックスに貼り付けます。
   5. **[Update]**をクリックします。
9. Azure AD クラシック ポータルで、シングル サインオンの構成確認を選択し、 **[次へ]**をクリックします。 
   
    ![Azure AD のシングル サインオン][10]
10. **[シングル サインオンの確認]** ページで、**[完了]** をクリックします。  
    
     ![Azure AD のシングル サインオン][11]

### <a name="create-an-azure-ad-test-user"></a>Azure AD のテスト ユーザーの作成
このセクションの目的は、Azure クラシック ポータルで Britta Simon というテスト ユーザーを作成することです。

![Azure AD ユーザーの作成][20]

**Azure AD でテスト ユーザーを作成するには、次の手順に従います。**

1. **Azure クラシック ポータル**の左側のナビゲーション ウィンドウで、**[Active Directory]** をクリックします。
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_09.png) 
2. **[ディレクトリ]** の一覧から、ディレクトリ統合を有効にするディレクトリを選択します。
3. 上部のメニューで **[ユーザー]**をクリックして、ユーザーの一覧を表示します。
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_03.png) 
4. 下部にあるツール バーで **[ユーザーの追加]** をクリックして、**[ユーザーの追加]** ダイアログ ボックスを開きます。 
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_04.png) 
5. **[このユーザーに関する情報の入力]** ダイアログ ページで、次の手順に従います。 
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_05.png)  
   1. [ユーザーの種類] として [組織内の新しいユーザー] を選択します。
   2. [ユーザー名] **ボックス**に「**BrittaSimon**」と入力します。
   3. **[次へ]**をクリックします。
6. **[ユーザー プロファイル]** ダイアログ ページで、次の手順に従います。 
   
   ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_06.png) 
   1. **[名]** ボックスに「**Britta**」と入力します。  
   2. **[姓]** ボックスに「**Simon**」と入力します。
   3. **[表示名]** ボックスに「**Britta Simon**」と入力します。
   4. **[ロール]** 一覧で **[ユーザー]** を選択します。
   5. **[次へ]**をクリックします。
7. **[一時パスワードの取得]** ダイアログ ページで、**[作成]** をクリックします。
   
    ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_07.png) 
8. **[一時パスワードの取得]** ダイアログ ページで、次の手順に従います。
   
   ![Azure AD のテスト ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/create_aaduser_08.png) 
   1. **[新しいパスワード]** の値を書き留めます。
   2. ページの下部にある **[完了]**」を参照してください。   

### <a name="create-a-flatter-files-test-user"></a>Flatter Files テスト ユーザーの作成
このセクションの目的は、Flatter Files で Britta Simon というユーザーを作成することです。

**Flatter Files で Britta Simon というユーザーを作成するには、次の手順に従います。**

1. **Flatter Files** 企業サイトに管理者としてサインオンします。
2. 左側のナビゲーション ウィンドウで、**[Settings]**、**[Users]** タブの順にクリックします。
   
    ![Flatter Files ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_09.png)
3. **[ユーザーの追加]**をクリックします。 
4. **[Add User]** ダイアログで、次の手順を実行します。
   
    ![Flatter Files ユーザーの作成](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_10.png)
   1. **[名]** ボックスに「**Britta**」と入力します。
   2. **[姓]** ボックスに「**Simon**」と入力します。 
   3. **[Email Address]** ボックスに、Britta の Azure クラシック ポータルの電子メール アドレスを入力します。
   4. **[Submit]**をクリックします。   

### <a name="assign-the-azure-ad-test-user"></a>Azure AD テスト ユーザーの割り当て
このセクションの目的は、Britta Simon に Flatter Files へのアクセスを許可することで、このユーザーが Azure のシングル サインオンを使用できるようにすることです。

![ユーザーの割り当て][200] 

**Flatter Files に Britta Simon を割り当てるには、次の手順に従います。**

1. Azure クラシック ポータルでアプリケーション ビューを開くために、ディレクトリ ビューでトップ メニューの **[アプリケーション]** をクリックします。
   
    ![ユーザーの割り当て][201] 
2. アプリケーションの一覧で **[Flatter Files]**を選択します。
   
    ![ユーザーの割り当て](./media/active-directory-saas-flatter-files-tutorial/tutorial_flatter_files_11.png) 
3. 上部のメニューで **[ユーザー]**をクリックします。
   
    ![ユーザーの割り当て][203] 
4. ユーザーの一覧で **[Britta Simon]**を選択します。
5. 下部にあるツール バーで **[割り当て]**をクリックします。
   
    ![ユーザーの割り当て][205]

### <a name="test-single-sign-on"></a>シングル サインオンのテスト
このセクションの目的は、アクセス パネルを使用して Azure AD のシングル サインオン構成をテストすることです。  

アクセス パネルで [Flatter Files] タイルをクリックすると、自動的に Flatter Files アプリケーションにサインオンします。

## <a name="additional-resources"></a>その他のリソース
* [SaaS アプリと Azure Active Directory を統合する方法に関するチュートリアルの一覧](active-directory-saas-tutorial-list.md)
* [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](active-directory-appssoaccess-whatis.md)

<!--Image references-->

[1]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_01.png
[2]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_02.png
[3]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_03.png
[4]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_04.png

[6]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_05.png
[10]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_06.png
[11]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_07.png
[20]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_100.png

[200]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_200.png
[201]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_201.png
[203]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_203.png
[204]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_204.png
[205]: ./media/active-directory-saas-flatter-files-tutorial/tutorial_general_205.png







