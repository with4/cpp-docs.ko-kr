---
title: "방법: Windows Forms 컨트롤에 명령 라우팅 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows Forms 컨트롤에 추가 명령 라우팅 [c + +]"
  - "Windows Forms 컨트롤 [c + +] 명령 라우팅"
ms.assetid: bf138ece-b463-442a-b0a0-de7063a760c0
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 방법: Windows Forms 컨트롤에 명령 라우팅 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView](../mfc/reference/cwinformsview-class.md) MFC 명령 (예를 들어 프레임 메뉴 항목 및 도구 모음 단추)를 처리할 수 있도록 하려면 사용자 정의 컨트롤에 명령 및 update 명령 UI 메시지를 라우팅합니다.  
  
 사용자 정의 컨트롤 사용 하 여 [ICommandTarget::Initialize](../Topic/ICommandTarget::Initialize.md) 의 명령 원본 개체에 대 한 참조를 저장 하 `m_CmdSrc`, 다음 예제와 같이 합니다. 사용 하 여 `ICommandTarget` mfcmifc80.dll에 대 한 참조를 추가 해야 합니다.  
  
 `CWinFormsView` 관리 되는 사용자 정의 컨트롤에 전달 하 여 몇 가지 공통 MFC 뷰 알림을 처리 합니다. 이러한 알림에 포함 된 [OnInitialUpdate](../Topic/IView::OnInitialUpdate.md), [OnUpdate](../Topic/IView::OnUpdate.md) 및 [OnActivateView](../Topic/IView::OnActivateView.md) 의 메서드는 [IView 인터페이스](../mfc/reference/iview-interface.md)합니다.  
  
 이 항목에서는 이전에 완료 된 [하는 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 및 [하는 방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.  
  
### <a name="to-create-the-mfc-host-application"></a>MFC 호스트 응용 프로그램을 만들려면  
  
1.  만든 Windows Forms 컨트롤 라이브러리를 열고 [하는 방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)합니다.  
  
2.  프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 여 수행할 수 있는 mfcmifc80.dll에 대 한 참조를 추가 **솔루션 탐색기**, 선택한 **추가**, **참조**, 다음 Microsoft Visual Studio 10.0\VC\atlmfc\lib를 탐색 하도록 합니다.  
  
3.  UserControl1.Designer.cs를 열고 다음 코드를 추가 문을 사용 하 여:  
  
    ```  
    using Microsoft.VisualC.MFC;  
    ```  
  
4.  또한 UserControl1.Designer.cs,이 줄을 변경 합니다.  
  
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
  
6.  다음 메서드 정의를 추가 `UserControl1` (만듭니다 MFC 컨트롤의 ID는 다음 단계에서).  
  
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
  
7.  MFC 응용 프로그램에서 만든 엽니다 [하는 방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)합니다.  
  
8.  호출할 메뉴 옵션을 추가 `singleMenuHandler`합니다.  
  
     이동 **리소스 뷰** (Ctrl + Shift + E) 확장은 **메뉴** 폴더를 두 번 클릭 하 고 **IDR_MFC02TYPE**합니다. 메뉴 편집기가 표시 됩니다.  
  
     아래쪽의 메뉴 옵션을 추가 **보기** 메뉴. 메뉴 옵션의 ID를 알 수는 **속성** 창입니다. 파일을 저장합니다.  
  
      **솔루션 탐색기**, Resource.h 파일을 열고, 방금 추가한 메뉴 옵션에 대 한 ID 값을 복사 및에 대 한 첫 번째 매개 변수로 해당 값을 붙여 넣습니다.는 `m_CmdSrc.AddCommandHandler` C# 프로젝트에서 호출 `Initialize` 메서드 (대체 `32771` 필요한 경우).  
  
9. 프로젝트를 빌드하고 실행합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     에 **디버그** 메뉴를 클릭 하 여 **디버깅 하지 않고 시작**합니다.  
  
     추가한 메뉴 옵션을 선택 합니다. .Dll에서 메서드가 호출 되도록 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [ICommandSource 인터페이스](../mfc/reference/icommandsource-interface.md)   
 [ICommandTarget 인터페이스](../mfc/reference/icommandtarget-interface.md)   
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)