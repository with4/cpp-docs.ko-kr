---
title: "방법: Windows Forms 컨트롤의 속성 및 메서드 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메서드 호출, Windows Forms 컨트롤"
  - "속성 호출"
  - "속성 호출, Windows Forms 컨트롤"
  - "메서드 호출, Windows Forms"
  - "Windows Forms 컨트롤[C++], 메서드"
  - "Windows Forms 컨트롤[C++], 속성"
ms.assetid: 6e647d8a-fdaa-4aa1-b3fe-04f15cff8eb3
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Windows Forms 컨트롤의 속성 및 메서드 호출
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)은 `WindowsControlLibrary1::UserControl1`에 대한 포인터가 아니라 <xref:System.Windows.Forms.Control?displayProperty=fullName>에 대한 포인터를 반환하므로 사용자 정의 컨트롤 형식의 멤버를 추가하고 이를 [IView::OnInitialUpdate](../Topic/IView::OnInitialUpdate.md)에서 초기화하는 것이 좋습니다.  이제 `m_ViewControl`을 사용하여 메서드와 속성을 호출할 수 있습니다.  
  
 이 항목에서는 [방법: 대화 상자에 사용자 정의 컨트롤 및 호스트 만들기](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md) 및 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)를 이미 완료한 것으로 간주합니다.  
  
### MFC 호스트 응용 프로그램을 만들려면  
  
1.  [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)에서 만든 MFC 응용 프로그램을 엽니다.  
  
2.  MFC02View.h에서 `CMFC02View` 클래스 선언의 public overrides 섹션에 다음 줄을 추가합니다.  
  
     `gcroot<WindowsFormsControlLibrary1::UserControl1 ^> m_ViewControl;`  
  
3.  OnInitialupdate에 대한 재정의를 추가합니다.  
  
     F4 키를 눌러 **속성** 창을 표시합니다.  **클래스 뷰**\(Ctrl\+Shift\+C\)에서 CMFC02View 클래스를 선택합니다.  **속성** 창에서 재정의를 나타내는 아이콘을 선택합니다.  OnInitialUpdate가 표시될 때까지 목록을 아래로 스크롤합니다.  Click on the drop down list and select \<Add\>.  In MFC02View.cpp. make sure the body of the OnInitialUpdate function is as follows:  
  
    ```  
    CWinFormsView::OnInitialUpdate();  
    m_ViewControl = safe_cast<WindowsFormsControlLibrary1::UserControl1 ^>(this->GetControl());  
    m_ViewControl->textBox1->Text = gcnew System::String("hi");  
    ```  
  
4.  프로젝트를 빌드하고 실행합니다.  
  
     **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     **디버그** 메뉴에서 **디버깅하지 않고 시작**을 클릭합니다.  
  
     텍스트 상자가 초기화됩니다.  
  
## 참고 항목  
 [Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)