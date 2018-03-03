---
title: "ATL 프로젝트에 개체 및 컨트롤 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.controls
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 319d130b9d8f17875aaa8bac15f546401457b963
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>ATL 프로젝트에 개체 및 컨트롤 추가
ATL 또는 MFC 기반 프로젝트에는 개체 또는 컨트롤을 추가 하는 ATL 코드 마법사 중 하나를 사용할 수 있습니다. 추가 각 COM 개체 또는 컨트롤에 대 한 마법사 레지스트리 스크립트 기반 지원 위한.rgs 파일 뿐만 아니라.cpp 및.h 파일을 생성 합니다. 다음 ATL 코드 마법사 Visual Studio에서 사용할 수 있습니다.  
  
||||  
|-|-|-|  
|[ATL 단순 개체](../../atl/reference/atl-simple-object-wizard.md)|[ATL 대화 상자](../../atl/reference/atl-dialog-wizard.md)|[ATL 컨트롤](../../atl/reference/atl-control-wizard.md)|  
|[ATL 속성 페이지](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page 구성 요소](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB 소비자](../../atl/reference/atl-ole-db-consumer-wizard.md)|  
|[MFC에 ATL 지원 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 구성 요소 마법사](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB 공급자](../../atl/reference/atl-ole-db-provider-wizard.md)|  
  
> [!NOTE]
>  프로젝트에 ATL 개체를 추가 하기 전에 세부 정보 및 개체 관련된 도움말 항목에 대 한 요구 사항을 검토 해야 합니다.  
  
### <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>개체 또는 ATL 컨트롤 마법사를 사용 하 여 컨트롤을 추가 하려면  
  
1.  솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **추가** 바로 가기 메뉴에서. 클릭 **클래스 추가**합니다.  
  
     [클래스 추가](../../ide/add-class-dialog-box.md) 대화 상자가 나타납니다.  
  
2.  ATL 폴더를 범주 창에서 선택한 템플릿 창에서 삽입 하는 개체를 선택 합니다. 클릭 **열려**합니다. 선택한 개체에 대 한 코드 마법사가 나타납니다.  
  
    > [!NOTE]
    >  MFC 프로젝트에 ATL 개체를 추가 하려면 기존 프로젝트에 ATL 지원을 추가 해야 합니다. 지침에 따라 이렇게 하려면 [MFC 프로젝트에 ATL 지원 추가](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)합니다.  
  
     또는 이전에 ATL 지원 추가 하지 않고 MFC 프로젝트에 ATL 개체를 추가 하려고 하면 Visual Studio 프로젝트에 추가 하는 ATL 지원 여부를 지정할 것인지 묻습니다. 클릭 **예** 프로젝트에 ATL 지원 추가 하 고 선택된 ATL 마법사를 엽니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL 프로젝트 마법사](../../atl/reference/atl-project-wizard.md)   
 [Visual c + + 프로젝트 형식](../../ide/visual-cpp-project-types.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)

