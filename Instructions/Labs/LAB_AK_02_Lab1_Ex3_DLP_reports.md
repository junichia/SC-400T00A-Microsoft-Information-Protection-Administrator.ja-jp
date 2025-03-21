---
ms.openlocfilehash: 05acea7ffe00c54d00c935da94f15ba402b23121
ms.sourcegitcommit: 2e9e5dd78a50682b1afef130c7c566b7d929f854
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2022
ms.locfileid: "137899363"
---
# <a name="lab-2---exercise-3---manage-dlp-reports"></a>ラボ 2 - 演習 3 - DLP レポートを管理する

あなたは Contoso Ltd. のコンプライアンス管理者、Joni Sherman です。データ損失防止の目的で、組織の Microsoft 365 テナントを構成する任務を負っています。 Contoso Ltd. は米国で自動車運転教習を行っている企業です。あなたには機密の顧客情報がこの組織から漏えいしないようにする役目があります。 新しいコンプライアンス責任者が DLP レポートの確認を支援することが通知されます。

### <a name="task-1---grant-access-to-dlp-reports"></a>タスク 1 - DLP レポートに対するアクセスの許可

この演習では、新しいコンプライアンス責任者に対して、DLP レポートに対するアクセスの許可を与えます。 このコンプライアンス責任者は技術系のユーザーではないため、レポートに目を通すだけで、DLP の構成に変更は行いません。

1. Client 1 VM (LON-CL1) に **lon-cl1\admin** アカウントでログインします。

2. **Microsoft Edge** で、 **https://compliance.microsoft.com** に移動して Microsoft 365 コンプライアンス ポータルに **MOD 管理者** admin@WWLxZZZZZZ.onmicrosoft.com としてログインします (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。  管理者のパスワードは、ラボ ホスティング プロバイダーから支給されます。

3. 左側のナビゲーション ペインで、 **[アクセス許可]** を選択し、 **[Microsoft Purviewソリューション]** の下にある **[役割]** を選択します。  **[Security Reader]** ロールの横にあるチェック ボックスをオンにします。

4. *[Security Reader]* ペインで、 **[メンバー]** 領域の **[編集]** を選択します。

5. **「メンバーの選択」** 、 **「+ 追加」** の順に選択します。

6. 「**Megan Bowen**」を検索し、名前の前にあるチェックボックスを選択して、 **「追加」** を選択します。

7. メンバー一覧が変更されていることを確認したら、 **「完了」** を選択します。

8. **[保存]** を選択します。 **[Security Reader]** ロール ペインを閉じます。

これで新しいコンプライアンス責任者に対して、Microsoft 365 コンプライアンス ポータルの DLP レポートに対するアクセスが許可されました。

### <a name="task-2---test-access-to-dlp-reports"></a>タスク 2 - DLP レポートに対するアクセスのテスト

このタスクでは、タスク 1 で許可した DLP レポートに対するアクセスが正しく適用されているかテストします。

1. Client 2 VM (LON-CL2) に **lon-cl2\admin** アカウントでログインします。

2. **Microsoft Edge** で、 **https://compliance.microsoft.com** に移動して Microsoft 365 コンプライアンス ポータルに **Megan Bowen** MeganB@WWLxZZZZZZ.onmicrosoft.com としてログインします (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。  Megan のパスワードは、ラボ ホスティング プロバイダーから支給されます。

3. 左側のナビゲーション ウィンドウで、 **「レポート」** を選択して、「レポート ダッシュボード」にアクセスします。

アクセスが構成され、新しいコンプライアンス責任者がコンプライアンス センターのレポートを閲覧できることが確認されました。

## <a name="you-have-completed-the-lab-2-proceed-to-lab-3---exercise-1"></a>これでラボ 2 は完了です。 ラボ 3 - 演習 1 に進む。
