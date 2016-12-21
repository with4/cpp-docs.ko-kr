---
title: "Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "Windows Forms 컨트롤 호스팅[C++]"
  - "MFC[C++], Windows Forms 지원"
  - "Windows Forms 컨트롤[C++], MFC 뷰로 호스팅"
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Forms 사용자 정의 컨트롤을 MFC 뷰로 호스팅
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC에서는 CWinFormsView 클래스를 사용하여 MFC 뷰에 Windows Forms 사용자 정의 컨트롤을 호스팅합니다.  MFC Windows Forms 뷰는 ActiveX 컨트롤입니다.  사용자 정의 컨트롤은 네이티브 뷰의 자식으로 호스팅되고 네이티브 뷰의 전체 클라이언트 영역을 차지합니다.  
  
 최종 결과는 [CFormView Class](../mfc/reference/cformview-class.md)에 사용되는 모델과 비슷합니다.  따라서 Windows Forms 디자이너를 사용할 수 있고 런타임에 리치 폼 기반 뷰를 만들 수 있습니다.  
  
 MFC Windows Forms 뷰는 ActiveX 컨트롤이므로 MFC 뷰와 동일한 `hwnd`가 없습니다.  또한 이를 [CView](../mfc/reference/cview-class.md) 뷰에 포인터로 전달할 수 없습니다.  일반적으로 .NET Framework 메서드를 사용하여 Windows Forms 뷰 작업을 수행하고 Win32는 자주 사용하지 않습니다.  
  
 MFC와 함께 사용 하는 Windows Forms을 보여 주는 샘플 응용 프로그램은 [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)을 참조하십시오.  
  
## 단원 내용  
 [방법: 사용자 정의 컨트롤 및 호스트 MDI 뷰 만들기](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [방법: Windows Forms 컨트롤에 명령 라우팅 추가](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [방법: Windows Forms 컨트롤의 속성 및 메서드 호출](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## 참고 항목  
 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [방법: 합성 컨트롤 제작](../Topic/How%20to:%20Author%20Composite%20Controls.md)