---
title: "ATL 속성 페이지 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property pages, adding
- ATL projects, adding property pages
- controls [ATL], property pages
ms.assetid: ddf92b49-42a2-46d2-b6b8-d37baedebeca
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 72a8644d81857b722fd50a7e852d215bb25a2fb2
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="adding-an-atl-property-page"></a>ATL 속성 페이지 추가
액티브 템플릿 라이브러리 (ATL) 속성 페이지에 프로젝트를 추가 하려면 프로젝트에 ATL 지원을 포함 하는 MFC 응용 프로그램 또는 ATL 응용 프로그램으로 만들어야 합니다. 사용할 수는 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만드는 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 대 한 ATL 지원을 구현 하 합니다.  
  
 컨트롤에 대 한 속성 페이지를 추가 하는 경우에 컨트롤 지원 해야 합니다는 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 인터페이스입니다. 이 인터페이스는 기본적으로 컨트롤의 파생 목록에 클래스 있습니다 [ATL 컨트롤 만들](../../atl/reference/adding-an-atl-control.md) 를 사용 하는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)합니다.  
  
> [!NOTE]
>  컨트롤 클래스에 없는 경우 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 파생 목록에 있습니다 수동으로 추가 해야 합니다.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>프로젝트에 ATL 속성 페이지를 추가 하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), ATL 속성 페이지를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **클래스 추가**합니다.  
  
3.  에 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 클릭 **ATL 속성 페이지** 클릭 하 고 **열려** 표시 하는 [ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)합니다.  
  
 컨트롤에 대 한 속성 페이지를 만든 후에 제공 해야는 [PROP_PAGE](property-map-macros.md#prop_page) 속성 맵에 컨트롤에 대 한 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../../atl/atl-com-property-pages.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [예: 속성 페이지 구현](../../atl/example-implementing-a-property-page.md)


