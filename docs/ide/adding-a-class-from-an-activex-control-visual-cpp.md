---
title: "ActiveX 컨트롤의 클래스 추가(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 클래스 추가"
  - "클래스[C++], 만들기"
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX 컨트롤의 클래스 추가(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사를 사용하면 사용 가능한 ActiveX 컨트롤의 인터페이스에서 MFC 클래스를 만들 수 있습니다.  [MFC 응용 프로그램](../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../mfc/reference/creating-an-mfc-dll-project.md) 또는 [MFC ActiveX 컨트롤](../mfc/reference/creating-an-mfc-activex-control.md)에 MFC 클래스를 추가할 수 있습니다.  
  
> [!NOTE]
>  ActiveX 컨트롤에서 클래스를 추가하기 위해 자동화가 설정된 MFC 프로젝트를 만들 필요는 없습니다.  
  
 ActiveX 컨트롤은 광범위한 OLE 기능을 지원하고 다양한 소프트웨어의 요구 사항에 맞게 사용자 지정할 수 있는 COM\(구성 요소 개체 모델\) 기반의 다시 사용 가능한 소프트웨어 구성 요소입니다.  ActiveX 컨트롤은 일반적인 ActiveX 컨트롤 컨테이너와 인터넷의 World Wide Web 웹 페이지 모두에 사용할 수 있도록 디자인되었습니다.  
  
### ActiveX 컨트롤의 MFC 클래스를 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 ActiveX 컨트롤 클래스를 추가하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ActiveX 컨트롤의 MFC 클래스**를 클릭한 다음 **열기**를 클릭하여 [ActiveX 컨트롤의 클래스 추가 마법사](../ide/add-class-from-activex-control-wizard.md)를 엽니다.  
  
 이 마법사에서 둘 이상의 인터페이스를 ActiveX 컨트롤에 추가할 수 있습니다.  마찬가지로, 마법사 세션 하나에서 둘 이상의 ActiveX 컨트롤로부터 클래스를 만들 수 있습니다.  
  
 시스템에 등록된 ActiveX 컨트롤에서 클래스를 추가할 수도 있고, ActiveX 컨트롤을 시스템에 먼저 등록하지 않고 형식 라이브러리 파일\(.tlb, .olb, .dll, .ocx, .exe\)에 있는 ActiveX 컨트롤에서 클래스를 추가할 수도 있습니다.  ActiveX 컨트롤 등록에 대한 자세한 내용은 [Registering OLE Controls](../mfc/reference/registering-ole-controls.md)을 참조하십시오.  
  
 마법사는 사용자가 선택한 ActiveX 컨트롤에서 추가하는 각 인터페이스에 대해 [CWnd](../mfc/reference/cwnd-class.md) 또는 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)에서 파생된 MFC 클래스를 만듭니다.  
  
## 참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)