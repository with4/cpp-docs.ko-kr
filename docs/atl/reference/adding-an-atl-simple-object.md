---
title: "ATL 단순 개체 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.classes.adding.atl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 개체 추가"
  - "ATL, 단순 개체"
  - "개체[ATL]"
ms.assetid: 9c57d2ef-0447-4c84-8982-3304b8e49847
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# ATL 단순 개체 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL\(Active Template Library\) 개체를 프로젝트에 추가하려면 프로젝트를 ATL 응용 프로그램이나 ATL을 지원하는 MFC 응용 프로그램으로 만들어야 합니다.  [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
 ATL 개체를 처음 만들 때 새로운 ATL 개체에 대한 COM 인터페이스를 정의하거나 클래스 뷰 바로 가기 메뉴의 [인터페이스 구현](../../ide/implement-interface-wizard.md) 명령을 사용하여 나중에 인터페이스를 추가할 수 있습니다.  
  
### ATL COM 프로젝트에 ATL 단순 개체를 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 ATL 단순 개체를 추가하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ATL 단순 개체**를 클릭한 다음 **열기**를 클릭하여 [ATL 단순 개체 마법사](../../atl/reference/atl-simple-object-wizard.md)를 표시합니다.  
  
4.  ATL 단순 개체 마법사의 [옵션](../../atl/reference/options-atl-simple-object-wizard.md) 페이지에서 프로젝트에 대한 추가 옵션을 설정합니다.  
  
5.  **마침**을 클릭하여 프로젝트에 해당 개체를 추가합니다.  
  
## 참고 항목  
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)   
 [ATL 프로젝트에 새 인터페이스 추가](../../atl/reference/adding-a-new-interface-in-an-atl-project.md)   
 [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md)   
 [메서드 추가](../../ide/adding-a-method-visual-cpp.md)   
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [일반 C\+\+ 클래스 추가](../../ide/adding-a-generic-cpp-class.md)