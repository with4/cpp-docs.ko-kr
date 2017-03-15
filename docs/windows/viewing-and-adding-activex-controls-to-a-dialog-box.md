---
title: "Viewing and Adding ActiveX Controls to a Dialog Box | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls.activex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dialog boxes [C++], adding ActiveX controls"
  - "Insert ActiveX Control command"
  - "ActiveX controls [C++], adding to dialog boxes"
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Viewing and Adding ActiveX Controls to a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio에서는 ActiveX 컨트롤을 대화 상자에 삽입할 수 있습니다.  
  
### 사용 가능한 ActiveX 컨트롤을 확인하려면  
  
1.  대화 상자 편집기에서 대화 상자를 엽니다.  
  
2.  대화 상자 본문에서 아무 곳이나 마우스 오른쪽 단추로 클릭합니다.  
  
3.  바로 가기 메뉴에서 **ActiveX 컨트롤 삽입**을 클릭합니다.  
  
     [ActiveX 컨트롤 삽입 대화 상자](../mfc/insert-activex-control-dialog-box.md)가 표시되고 시스템에 있는 모든 ActiveX 컨트롤을 보여 줍니다. 대화 상자 아래쪽에 ActiveX 컨트롤 파일 경로가 표시됩니다.  
  
### 대화 상자에 ActiveX 컨트롤을 추가하려면  
  
1.  [ActiveX 컨트롤 삽입 대화 상자](../mfc/insert-activex-control-dialog-box.md)에서 대화 상자에 추가할 컨트롤을 선택하고 **확인**을 클릭합니다.  
  
     컨트롤이 대화 상자에 표시되고, 이 대화 상자에서 컨트롤을 편집하거나 다른 컨트롤처럼 컨트롤용 처리기를 만들 수 있습니다.  
  
    > [!NOTE]
    >  ActiveX 컨트롤을 [도구 상자 창](../Topic/Toolbox.md)에 추가할 수 있습니다. 자세한 내용은 [도구 상자의 항목 및 탭 관리](http://msdn.microsoft.com/ko-kr/21285050-cadd-455a-b1f5-a2289a89c4db)를 참조하세요.  
  
    > [!CAUTION]
    >  시스템에 일부 ActiveX 컨트롤을 배포하지 못할 수 있습니다. 컨트롤을 설치한 소프트웨어에 대한 사용권 계약을 참조하거나 소프트웨어 회사에 문의하세요.  
  
     쉬운 액세스를 위해 도구 상자 창에 컨트롤을 배치할 수 있습니다. 자세한 내용은 [도구 상자 대화 상자 사용자 지정](http://msdn.microsoft.com/ko-kr/bd07835f-18a8-433e-bccc-7141f65263bb)을 참조하세요.  
  
 관리되는 프로젝트에 리소스를 추가하는 방법은 *.NET Framework 개발자 가이드*에서 [응용 프로그램의 리소스](../Topic/Resources%20in%20Desktop%20Apps.md)를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/ko-kr/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)을 참조하세요.  
  
 **요구 사항**  
  
 Win32  
  
## 참고 항목  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)