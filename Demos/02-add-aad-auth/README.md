# <a name="completed-module-add-azure-ad-authentication"></a>完了したモジュール: Azure AD 認証を追加する

このディレクトリにあるプロジェクトのバージョンは、「 [Azure AD 認証を追加](https://docs.microsoft.com/graph/training/ruby-tutorial?tutorial-step=3)する」のチュートリアルを完了することを反映しています。 このバージョンのプロジェクトを使用する場合は、「[予定表データを取得](https://docs.microsoft.com/graph/training/ruby-tutorial?tutorial-step=4)する」からチュートリアルの残りの部分を完了する必要があります。

> **注:**「[アプリをポータルに登録](https://docs.microsoft.com/graph/training/ruby-tutorial?tutorial-step=2)する」で示されているように、アプリ登録ポータルに既にアプリケーションを登録していることを前提としています。 このバージョンのサンプルは、次のように構成する必要があります。
>
> 1. ファイルの`./config/oauth_environment_variables.rb.example`名前を`oauth_environment_variables.rb`に変更します。
> 1. `oauth_environment_variables.rb`ファイルを編集し、次のように変更します。
>     1. を`YOUR_APP_ID_HERE`アプリ登録ポータルで取得した**アプリケーション Id**に置き換えます。
>     1. を`YOUR APP PASSWORD HERE`アプリ登録ポータルから取得したパスワードに置き換えます。