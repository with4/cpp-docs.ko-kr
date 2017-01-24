---
title: "방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크 | Microsoft Docs"
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
  - "이벤트 처리, .NET/네이티브 interop"
  - "이벤트 처리, 관리되는/네이티브 interop"
  - "이벤트 처리, C++에서 .NET 싱크"
  - "이벤트 처리, C++에서 Windows Forms 이벤트 처리"
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

네이티브 C\+\+ 클래스를 사용하면 Windows Forms 컨트롤이나 MFC 매크로 맵 형식의 다른 폼에서 발생한 관리되는 이벤트의 콜백을 받을 수 있습니다.  뷰와 대화 상자에서의 이벤트 싱크는 컨트롤에 대해 동일한 작업을 수행하는 경우와 비슷합니다.  
  
 이를 수행하려면 다음 작업이 필요합니다.  
  
-   [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md)를 사용하여 `OnClick` 이벤트 처리기를 컨트롤에 연결합니다.  
  
-   [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md), [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md) 및 [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md)를 사용하여 대리자 맵을 만듭니다.  
  
 이 샘플에서는 [방법: Windows Forms에서 DDX\/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)에서 수행한 작업을 계속합니다.  
  
 이제 MFC 컨트롤\(`m_MyControl`\)을 관리되는 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 `OnClick`이라는 관리되는 이벤트 처리기 대리자에 연결합니다.  
  
### OnClick 이벤트 처리기를 연결하려면  
  
1.  다음 코드를 BOOL CMFC01Dlg::OnInitDialog 구현에 추가합니다.  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  CMFC01Dlg : public CDialog 클래스 선언의 public 섹션에 다음 코드를 추가합니다.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  끝으로 `OnClick`의 구현을 CMFC01Dlg.cpp에 추가합니다.  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## 참고 항목  
 [MAKE\_DELEGATE](../Topic/MAKE_DELEGATE.md)   
 [BEGIN\_DELEGATE\_MAP](../Topic/BEGIN_DELEGATE_MAP.md)   
 [END\_DELEGATE\_MAP](../Topic/END_DELEGATE_MAP.md)   
 [EVENT\_DELEGATE\_ENTRY](../Topic/EVENT_DELEGATE_ENTRY.md)