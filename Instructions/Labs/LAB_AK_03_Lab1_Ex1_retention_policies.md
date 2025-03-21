---
ms.openlocfilehash: a826e5a9cac44bd65f765cfe1322731747535611
ms.sourcegitcommit: b50f9a265cf3a73ace7cbec4b5cb6f7420acc139
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "141151316"
---
# <a name="lab-3---exercise-1---configure-retention-policies"></a>ラボ 3 - 演習 1 - 保持ポリシーを構成する

この演習では、Contoso Ltd. のシステム管理者である Joni Sherman のロールを実行します。 この企業はテキサスを本拠地としており、記録は 3 年を経過したら削除しても違法ではない、という州法を遵守するために保持ポリシーを実装する必要があります。 

この法律を遵守するために、組織ではすべてのアイテムを 3 年間保持する保持計画を作成しています。


### <a name="task-1--create-company-wide-retention-policy"></a>タスク 1 – 全社的な保持ポリシーを作成する

この演習では、全社的な保持ポリシーを作成し、保持期間を適用し、ポリシーを適用する場所を設定します。

1. Client 1 VM (LON-CL1) に **lon-cl1\admin** アカウントでログインします。

2. **Microsoft Edge** で、 **https://compliance.microsoft.com** に移動して Microsoft 365 コンプライアンス ポータルに **Joni Sherman** JoniS@WWLxZZZZZZ.onmicrosoft.com としてログインします (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。  Joni のパスワードは、ラボ ホスティング プロバイダーから支給されます。

3. **Microsoft 365 コンプライアンス** ポータルの左側のナビゲーション ペインで **[ポリシー]** を選択し、 **[データ]** で **[保持]** を選択します。

4. **[データライフサイクル管理]** ページの **[アイテム保持ポリシー]** タブで、 **[+ 新しいアイテム保持ポリシー]** を選択します。

5. **「保持ポリシーの名前を設定」** ページの **「名前」** と **「説明」** に、次の情報を入力します。

    - 名前: 会社全体
    - 説明: Teams を除くすべての場所

6. **[次へ]** ボタンを選択します。  

7. **[作成するアイテム保持ポリシーの種類を選択する]** ページで、 **[静的]** を選択して、 **[次へ]** を選択します。

8. **「ポリシーを適用する場所を選択する」** 領域で、Exchange メール、SharePoint サイト、OneDrive アカウント、 Microsoft 365 グループが選択されていることを確認し、 **「次へ」** を選択します。

9. **「コンテンツを保持するか、削除するか、またはその両方を行うかを決定する」** ページで、 **「特定の期間のアイテムを保持する」** セクションで、次の情報を入力します。

    - [特定の期間アイテムを保持]:ドロップダウン リストから **[カスタム]** を選択します。
    - [年] フィールドを **[3]** に変更します。
    - **保持期間開始の条件**:アイテムの最終更新日時

10. **[次へ]** ボタンを選択します。

11. **「確認と完了」** ページで、 **「送信」** ボタンを選択します。

12. ポリシーが作成されたら、 **「完了」** を選択します。

Exchange メール、Microsoft 365 グループ、OneDrive、SharePoint サイトの場所に対する保持ポリシーが正常に作成されました。 この保持ポリシーでは、これらの場所にあるアイテムを、アイテムの最終変更日から 3 年間保持します。 このポリシーがテナントに適用されるまでに最大 24 時間かかる場合がありますが、次のステップに進むことができます。

### <a name="task-2--create-location-based-retention-policies-with-filter"></a>タスク 2 – フィルター付きの、場所に基づく保持ポリシーを作成する

ここでは、Teams の場所の保持ポリシーを作成します。 Teams のチャネルにはドキュメントを含めることができるで、それらはすべて保持されます。 組織では、限られた数のユーザーに Teams のチャットの保持期間を要求することにしました。

1. Client 1 VM (LON-CL1) には **lon-cl1\admin** アカウントでログインし、Microsoft 365 には **Joni Sherman** としてログインしておく必要があります。 

2. **Microsoft Edge** に、Microsoft 365 コンプライアンス ポータルのタブがまだ開かれているはずです。 その場合は、それを選択して次の手順に進みます。 閉じた場合は、新しいタブで **https://compliance.microsoft.com** に移動します。

3. **Microsoft 365 コンプライアンス** ポータルの左側のナビゲーション ペインで **[ポリシー]** を選択し、 **[データ]** で **[保持]** を選択します。

4. **「データ ライフサイクル管理」** ページの **「アイテム保持ポリシー」** タブで、 **「+ アイテム保持ポリシーの新規作成」** を選択します。

5. **「アイテム保持ポリシーの名前を設定」** ページの **「名前」** と **「説明」** に、次の情報を入力します。

    - **[名前]** : Teams 保持
    - **[説明]** : Teams の場所に対する保持

6. **[次へ]** ボタンを選択します。

7. **[作成するアイテム保持ポリシーの種類を選択する​]** ページで、 **[静的]** を選択してから、 **[次へ]** を選択します。

8. **「ポリシーを適用する場所の選択」** ページで、次の設定を入力します。

    - [場所]: **[Teams のチャネル メッセージ]**  
    - [場所]: **[Teams のチャット]**
    - 他のすべての場所を **[無効]** にします。

9. [場所]: **[Teams のチャット]** で、 **[すべてのユーザー]** の下のテキスト リンクで **[編集]** を選択します。

10. **「Teams チャット」** ペインで、次のユーザーを追加します。 
    - Adele Vance
    - Pradeep Gupta

    注: これらの 2 人のユーザーを追加することにより、Teams チャットに含まれる設定が「すべてのチーム」から追加した 2 人のユーザーのみに変更されました。

11. **「完了」** ボタンを選択します。

12. 「場所」ページに、次の通知が表示されます。**2 人のユーザー** が追加されました

13. **[次へ]** ボタンを選択します。

14. **「コンテンツを保持するか、削除するか、またはその両方を行うかを決定する」** ページで、 **「特定の期間のアイテムを保持」** セクションで、次の情報を入力します。

    - [特定の期間アイテムを保持]:ドロップダウン リストから **[カスタム]** を選択します。
    - [年] フィールドを **[3]** に変更します。
    - **保持期間開始の条件**:アイテムの最終更新日時


15. **[次へ]** ボタンを選択します。

16. **「確認と完了」** ページで、 **「送信」** ボタンを選択します。

17. ポリシーが正常に作成されたら、 **「完了」** を選択します。

Teams の場所に対する保持ポリシーが正常に作成されました。 すべての Teams チャネルの場所に 3 年間の保持期間を設定しました。 特定のユーザーにのみ適用されるように、Teams チャットの場所のフィルターを設定しました。

### <a name="task-3--create-retention-policy-via-powershell"></a>タスク 3 – PowerShell で保持ポリシーを作成する

PowerShell を使用して同じ保持ポリシーを作成します

1. Client 1 VM (LON-CL1) に **lon-cl1\admin** アカウントでログインします。

2. マウスの右ボタンで Windows ボタンを選択して管理者特権で PowerShell ウィンドウを開き、 **「Windows PowerShell (管理者)」** を選択します。「ユーザー アカウント制御」ウィンドウが表示されたら、 **「はい」** を選択します。

3. 次のコマンドレットを使用して、テナントのセキュリティ/コンプライアンス センターに接続します。以下のコマンドで「コマンドが見つからない」というエラー発生する場合は、**Install-Module ExchangeOnlineManagement** コマンドを先に実行してください。

    `Connect-IPPSSession`

4. サインインを要求するダイアログ ボックスが表示された場合は、**MOD 管理者** admin@WWLxZZZZZZ.onmicrosoft.com としてサインインします (ZZZZZZ はラボ ホスティング プロバイダーから支給された固有のテナント ID)。  管理者のパスワードは、ラボ ホスティング プロバイダーから支給されます。

5. 次のコマンドレットを実行して、Teams を除くすべての場所に対する最初の保持ポリシーを作成します。

    `New-RetentionCompliancePolicy -Name "Company Wide PS" -ExchangeLocation All -ModernGroupLocation All -PublicFolderLocation All -SharePointLocation All -OneDriveLocation All`

6. 次のコマンドレットを実行して、保持期間を設定します。単位は、変更日を基準にした日数を使用します。
    
    `New-RetentionComplianceRule -Name "Company Wide PS Rule" -Policy "Company Wide PS" -RetentionDuration 1095 -ExpirationDateOption ModificationAgeInDays -RetentionComplianceAction Keep`

7. 次のコマンドレットを実行して、Teams の場所に対する 2 つ目の保持ポリシーを作成します。

    `New-RetentionCompliancePolicy -Name "Teams Retention PS" -TeamsChannelLocation All -TeamsChatLocation "Adele Vance", "Pradeep Gupta"`

8. 次のコマンドレットを実行して、日数を単位として保持期間を設定します。

    `New-RetentionComplianceRule -Name "Teams Retention PS Rule" -Policy "Teams Retention PS" -RetentionDuration 1095 -RetentionComplianceAction Keep`

PowerShell を使って保持期間を 3 年に設定した保持ポリシーを正常に作成しました。

# <a name="proceed-to-lab-3---exercise-2"></a>ラボ 3 - 演習 2 に進む
