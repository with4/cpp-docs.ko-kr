---
title: "ATL 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 컨트롤 추가"
  - "컨트롤[ATL], 프로젝트에 추가"
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# ATL 컨트롤 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 마법사를 사용하여 모든 잠재적 컨테이너에 대해 인터페이스를 지원하는 프로젝트에 사용자 인터페이스 개체를 추가합니다.  이러한 인터페이스를 지원하려면 프로젝트를 ATL 응용 프로그램이나 ATL을 지원하는 MFC 응용 프로그램으로 만들어야 합니다.  [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
### ATL 컨트롤을 프로젝트에 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 ATL 단순 개체를 추가하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ATL 컨트롤**을 클릭한 다음 **추가**를 클릭하여 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)를 표시합니다.  
  
 **ATL 컨트롤 마법사**를 사용하여 다음 세 가지 중 한 가지 형식의 컨트롤을 만들 수 있습니다.  
  
-   표준 컨트롤  
  
-   복합 컨트롤  
  
-   DHTML 컨트롤  
  
 또한 마법사의 **옵션** 페이지에서 **최소 컨트롤**을 선택하여 컨트롤의 크기를 줄이고 대부분의 컨테이너에서 사용하지 않는 인터페이스를 제거할 수 있습니다.  
  
## 참고 항목  
 [Adding Functionality to the Composite Control](../../atl/adding-functionality-to-the-composite-control.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATLFire Sample](http://msdn.microsoft.com/ko-kr/5b2649f1-f45b-4cfb-9c4b-4d9459c26b09)