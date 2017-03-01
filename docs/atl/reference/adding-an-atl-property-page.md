---
title: "ATL 속성 페이지를 추가 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 7b6a6220a33890d99e6fb2bd81ce832b38720c50
ms.lasthandoff: 02/24/2017

---
# <a name="adding-an-atl-property-page"></a>ATL 속성 페이지를 추가합니다.
프로젝트에는 라이브러리 ATL (액티브 템플릿) 속성 페이지를 추가 하려면 프로젝트에 ATL 지원을 포함 하는 MFC 응용 프로그램 또는 ATL 응용 프로그램으로 만들어야 합니다. 사용할 수는 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md) ATL 응용 프로그램을 만드는 또는 [MFC 응용 프로그램에 ATL 개체를 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC 응용 프로그램에 대 한 ATL 지원을 구현 하기 위해.  
  
 컨트롤을 지원 해야 컨트롤에 대 한 속성 페이지를 추가 하는 경우는 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 인터페이스입니다. 기본적으로이 인터페이스는 파생 목록 컨트롤의 클래스 있습니다 [ATL 컨트롤 만들](../../atl/reference/adding-an-atl-control.md) 를 사용 하 여는 [ATL 컨트롤 마법사](../../atl/reference/atl-control-wizard.md)합니다.  
  
> [!NOTE]
>  컨트롤 클래스에 없는 경우 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 파생 목록에 있습니다 수동으로 추가 해야 합니다.  
  
### <a name="to-add-an-atl-property-page-to-your-project"></a>프로젝트에 ATL 속성 페이지를 추가 하려면  
  
1.  **솔루션 탐색기** 또는 [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)를 ATL 속성 페이지를 추가 하려면 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴를 클릭 하 여 **추가** 클릭 하 고 **클래스 추가**합니다.  
  
3.  에 [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자의 템플릿 창에서 클릭 **ATL 속성 페이지** 클릭 하 고 **열려** 표시 하는 [ATL 속성 페이지 마법사](../../atl/reference/atl-property-page-wizard.md)합니다.  
  
 컨트롤에 대 한 속성 페이지를 만든 후에 제공 해야는 [PROP_PAGE](http://msdn.microsoft.com/library/2155973e-b96c-4385-bf85-5d6112c969b8) 컨트롤에 대 한 속성 맵의 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../../atl/atl-com-property-pages.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [예: 속성 페이지 구현](../../atl/example-implementing-a-property-page.md)


