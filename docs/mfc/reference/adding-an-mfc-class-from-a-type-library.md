---
title: "형식 라이브러리에서 MFC 클래스 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스[C++], MFC 추가"
  - "MFC, 형식 라이브러리에서 클래스 추가"
  - "형식 라이브러리, MFC 클래스 추가"
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 형식 라이브러리에서 MFC 클래스 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사에서는 사용 가능한 형식 라이브러리의 인터페이스에서 MFC 클래스를 만듭니다.  [MFC 응용 프로그램](../../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md) 또는 [MFC ActiveX 컨트롤](../../mfc/reference/creating-an-mfc-activex-control.md)에 MFC 클래스를 추가할 수 있습니다.  
  
> [!NOTE]
>  형식 라이브러리에서 클래스를 추가하기 위해 자동화가 설정된 MFC 프로젝트를 만들 필요는 없습니다.  
  
 형식 라이브러리에는 구성 요소에 의해 노출된 인터페이스에 대한 이진 설명이 포함되며, 여기에는 메서드의 매개 변수 및 반환 형식과 함께 메서드가 정의되어 있습니다.  Typelib 마법사에서 클래스 추가의 **사용 가능한 형식 라이브러리** 목록에 나타나도록 형식 라이브러리를 등록해야 합니다.  자세한 내용은 MSDN Library의 “Inside Distributed COM: Type Libraries and Language Integration”을 참조하십시오.  
  
### 형식 라이브러리에서 MFC 클래스를 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 클래스를 추가하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **TypeLib의 MFC 클래스**를 클릭한 다음 **열기**를 클릭하여 [Typelib에서 클래스 추가 마법사](../../mfc/reference/add-class-from-typelib-wizard.md)를 표시합니다.  
  
 이 마법사에서 형식 라이브러리에는 둘 이상의 클래스를 추가할 수 있습니다.  마찬가지로 단일 마법사 세션으로 둘 이상의 형식 라이브러리의 클래스를 추가할 수 있습니다.  
  
 마법사에서는 사용자가 선택된 형식 라이브러리에서 추가하는 각 인터페이스에 대해 [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)에서 파생된 MFC 클래스를 만듭니다.  `COleDispatchDriver`는 클라이언트 쪽 OLE 자동화를 구현합니다.  
  
## 참고 항목  
 [자동화 클라이언트](../../mfc/automation-clients.md)   
 [자동화 클라이언트: 형식 라이브러리 사용](../../mfc/automation-clients-using-type-libraries.md)