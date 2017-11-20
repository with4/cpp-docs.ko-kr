---
title: "방법: 추가 명령 라우팅 windows Forms 컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- command routing [C++], adding to Windows Forms controls
- Windows Forms controls [C++], command routing
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21f3fda51f9df72d9af78a03783771e74fbf3370
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-add-command-routing-to-the-windows-forms-control"></a>방법: Windows Forms 컨트롤에 명령 라우팅 추가
[CWinFormsView](../mfc/reference/cwinformsview-class.md) MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)을 처리할 수 있도록 허용 하는 사용자 정의 컨트롤에 명령 및 명령 업데이트 UI 메시지를 라우팅합니다.  
  
 사용자 정의 컨트롤 사용 하 여 [ICommandTarget::Initialize](../mfc/reference/icommandtarget-interface.md#initialize) 에서 명령 원본 개체에 대 한 참조를 저장 하 `m_CmdSrc`다음 예제에 나온 것 처럼 합니다. 사용 하도록 `ICommandTarget` mfcmifc80.dll에 대 한 참조를 추가 해야 합니다.  
  
 `CWinFormsView`관리 되는 사용자 정의 컨트롤에 전달 하 여 몇 가지 일반적인 MFC 뷰 알림을 처리 합니다. 이러한 알림에 포함 된 [OnInitialUpdate](../mfc/reference/iview-interface.md#oninitialupdate), [OnUpdate](../mfc/reference/iview-interface.md#onupdate) 및 [OnActivateView](../mfc/reference/iview-interface.md#onactivateview) 메서드.  
  
 이 항목에서는 이전에 완료 된 [하는 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 및 [하는 방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면  
  
1.  만든 Windows Forms 컨트롤 라이브러리를 열고 [하는 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.  
  
2.  프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 여 수행할 수 있는 mfcmifc80.dll에 대 한 참조를 추가 **솔루션 탐색기**선택한 **추가**, **참조**, 다음 검색 하 고 Microsoft Visual Studio 10.0\VC\atlmfc\lib 합니다.  
  
3.  UserControl1.Designer.cs를 열고 다음 코드를 추가 문을 사용 하 여:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  또한 UserControl1.Designer.cs를이 줄을 변경 합니다.  
  
    ```  
    partial class UserControl1  
    ```  
  
     다음과 같이 변경 하려면  
  
    ```  
    partial class UserControl1 : System.Windows.Forms.UserControl, ICommandTarget  
    ```  
  
5.  에 대 한 클래스 정의의 첫 번째 줄으로 추가 `UserControl1`:  
  
    ```  
    private ICommandSource m_CmdSrc;  
    ```  
  
6.  에 다음과 같은 메서드 정의 추가 `UserControl1` (MFC 컨트롤의 ID에서에서 만들 다음 단계):  
  
    ```  
    public void Initialize (ICommandSource cmdSrc)  
    {  
       m_CmdSrc = cmdSrc;  
       // need ID of control in MFC dialog and callback function   
       m_CmdSrc.AddCommandHandler(32771, new CommandHandler (singleMenuHandler));  
    }  
  
    private void singleMenuHandler (uint cmdUI)  
    {  
       // User command handler code  
       System.Windows.Forms.MessageBox.Show("Custom menu option was clicked.");  
    }  
    ```  
  
7.  만든 MFC 응용 프로그램을 열고 [하는 방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.  
  
8.  호출 하는 메뉴 옵션을 추가 `singleMenuHandler`합니다.  
  
     로 이동 **리소스 뷰** (Ctrl + Shift + E)를 확장 하 고는 **메뉴** 폴더를 찾아 두 번 클릭 **IDR_MFC02TYPE**합니다. 메뉴 편집기가 표시 됩니다.  
  
     메뉴 옵션을 맨 아래에 추가 된 **보기** 메뉴. 메뉴 옵션에서의 ID를 확인할 수는 **속성** 창. 파일을 저장합니다.  
  
     **솔루션 탐색기**, Resource.h 파일을 열고 방금 추가한 메뉴 옵션에 대 한 ID 값을 복사 및 첫 번째 매개 변수를 해당 값 데이터 형식에서 `m_CmdSrc.AddCommandHandler` C# 프로젝트에서 호출 `Initialize` ( 교체메서드`32771` 필요한 경우).  
  
9. 프로젝트를 빌드하고 실행합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
     추가한 메뉴 옵션을 선택 합니다. 공지.dll의 메서드가 호출 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource 인터페이스](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget 인터페이스](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](http://msdn.microsoft.com/Library/22096734-e074-4aca-8523-4b15590109f9)