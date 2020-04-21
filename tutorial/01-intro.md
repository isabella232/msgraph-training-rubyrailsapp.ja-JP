<!-- markdownlint-disable MD002 MD041 -->

<span data-ttu-id="5e148-101">このチュートリアルでは、Microsoft Graph API を使用してユーザーの予定表情報を取得する Ruby on Rails web アプリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e148-101">This tutorial teaches you how to build a Ruby on Rails web app that uses the Microsoft Graph API to retrieve calendar information for a user.</span></span>

> [!TIP]
> <span data-ttu-id="5e148-102">完成したチュートリアルをダウンロードするだけで済む場合は、2つの方法でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5e148-102">If you prefer to just download the completed tutorial, you can download it in two ways.</span></span>
>
> - <span data-ttu-id="5e148-103">[Ruby クイックスタート](https://developer.microsoft.com/graph/quick-start?platform=option-ruby)をダウンロードして、作業コードを分単位で取得します。</span><span class="sxs-lookup"><span data-stu-id="5e148-103">Download the [Ruby quick start](https://developer.microsoft.com/graph/quick-start?platform=option-ruby) to get working code in minutes.</span></span>
> - <span data-ttu-id="5e148-104">[GitHub リポジトリ](https://github.com/microsoftgraph/msgraph-training-rubyrailsapp)をダウンロードするか、クローンを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e148-104">Download or clone the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-rubyrailsapp).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5e148-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="5e148-105">Prerequisites</span></span>

<span data-ttu-id="5e148-106">このチュートリアルを開始する前に、開発用のコンピューターに[Ruby](https://www.ruby-lang.org/en/downloads/)がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e148-106">Before you start this tutorial, you should have [Ruby](https://www.ruby-lang.org/en/downloads/) installed on your development machine.</span></span> <span data-ttu-id="5e148-107">Ruby を使用していない場合は、「ダウンロードオプション」の前のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e148-107">If you do not have Ruby, visit the previous link for download options.</span></span>

<span data-ttu-id="5e148-108">また、Outlook.com 上のメールボックスを持つ個人の Microsoft アカウント、または Microsoft 職場または学校のアカウントを所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e148-108">You should also have either a personal Microsoft account with a mailbox on Outlook.com, or a Microsoft work or school account.</span></span> <span data-ttu-id="5e148-109">Microsoft アカウントを持っていない場合は、無料のアカウントを取得するためのオプションがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="5e148-109">If you don't have a Microsoft account, there are a couple of options to get a free account:</span></span>

- <span data-ttu-id="5e148-110">[新しい個人用 Microsoft アカウントにサインアップ](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1)することができます。</span><span class="sxs-lookup"><span data-stu-id="5e148-110">You can [sign up for a new personal Microsoft account](https://signup.live.com/signup?wa=wsignin1.0&rpsnv=12&ct=1454618383&rver=6.4.6456.0&wp=MBI_SSL_SHARED&wreply=https://mail.live.com/default.aspx&id=64855&cbcxt=mai&bk=1454618383&uiflavor=web&uaid=b213a65b4fdc484382b6622b3ecaa547&mkt=E-US&lc=1033&lic=1).</span></span>
- <span data-ttu-id="5e148-111">[Office 365 開発者プログラムにサインアップ](https://developer.microsoft.com/office/dev-program)して、無料の office 365 サブスクリプションを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5e148-111">You can [sign up for the Office 365 Developer Program](https://developer.microsoft.com/office/dev-program) to get a free Office 365 subscription.</span></span>

> [!NOTE]
> <span data-ttu-id="5e148-112">このチュートリアルは、Ruby バージョン2.6.5 を使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="5e148-112">This tutorial was written with Ruby version 2.6.5.</span></span> <span data-ttu-id="5e148-113">このガイドの手順は、他のバージョンでは動作しますが、テストされていません。</span><span class="sxs-lookup"><span data-stu-id="5e148-113">The steps in this guide may work with other versions, but that has not been tested.</span></span>

## <a name="feedback"></a><span data-ttu-id="5e148-114">フィードバック</span><span class="sxs-lookup"><span data-stu-id="5e148-114">Feedback</span></span>

<span data-ttu-id="5e148-115">このチュートリアルに関するフィードバックは、 [GitHub リポジトリ](https://github.com/microsoftgraph/msgraph-training-rubyrailsapp)に記入してください。</span><span class="sxs-lookup"><span data-stu-id="5e148-115">Please provide any feedback on this tutorial in the [GitHub repository](https://github.com/microsoftgraph/msgraph-training-rubyrailsapp).</span></span>
