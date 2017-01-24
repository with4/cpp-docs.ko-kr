---
title: "ATL 속성 페이지 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 속성 페이지 추가"
  - "컨트롤[ATL], 속성 페이지"
  - "속성 페이지, 추가"
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 속성 페이지 추가
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL\(Active Template Library\) 속성 페이지를 프로젝트에 추가하려면 프로젝트를 ATL 응용 프로그램이나 ATL을 지원하는 MFC 응용 프로그램으로 만들어야 합니다.  [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)를 사용하여 ATL 응용 프로그램을 만들거나, [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)하여 MFC 응용 프로그램에 ATL 지원을 구현할 수 있습니다.  
  
 컨트롤에 대한 속성 페이지를 추가할 경우 해당 컨트롤에서는 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 인터페이스를 지원해야 합니다.  기본적으로 이 인터페이스는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md) 사용하여 [ATL 컨트롤을 만들](../../atl/reference/adding-an-atl-control.md) 때 컨트롤 클래스의 파생 목록에 있습니다.  
  
> [!NOTE]
>  컨트롤 클래스의 파생 목록에 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)이 없는 경우 직접 추가해야 합니다.  
  
### 프로젝트에 ATL 속성 페이지를 추가하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 ATL 속성 페이지를 추가하려는 프로젝트의 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
2.  바로 가기 메뉴에서 **추가**를 클릭한 다음 **클래스 추가**를 클릭합니다.  
  
3.  [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 **ATL 속성 페이지**를 클릭한 다음 **열기**를 클릭하여 [ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)를 엽니다.  
  
 컨트롤에 대한 속성 페이지를 만든 후에는 컨트롤에 대한 속성 맵에 [PROP\_PAGE](../Topic/PROP_PAGE.md) 엔트리를 제공해야 합니다.  
  
## 참고 항목  
 [속성 페이지](../../atl/atl-com-property-pages.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Example: Implementing a Property Page](../../atl/example-implementing-a-property-page.md)