---
title: "속성 페이지 (ATL) 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8985499c76a7dc65523a5c2904bcb774a4364d41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-property-pages"></a>속성 페이지를 지정합니다.
ActiveX 컨트롤을 만들 때 컨트롤의 속성을 설정 하는 데 사용할 수 있는 속성 페이지와 연결 하려는 경우가 많습니다. 컨테이너 사용을 제어는 **ISpecifyPropertyPages** 인터페이스를 확인할 사용자 컨트롤의 속성을 설정 하는 속성 페이지를 사용할 수 있습니다. 컨트롤에 대해이 인터페이스를 구현 해야 합니다.  
  
 구현 하려면 **ISpecifyPropertyPages** ATL을 사용 하 여 다음 단계를 수행 합니다.  
  
1.  클래스를 파생 [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)합니다.  
  
2.  에 대 한 항목을 추가 **ISpecifyPropertyPages** 클래스의 COM 맵에 있습니다.  
  
3.  추가 [PROP_PAGE](reference/property-map-macros.md#prop_page) 항목 컨트롤과 연결 된 각 페이지에 대 한 속성 매핑이을 합니다.  
  
> [!NOTE]
>  사용 하 여 표준 컨트롤을 생성 하는 경우는 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)를 추가 해야만 `PROP_PAGE` 속성 맵에 항목입니다. 마법사는 다른 단계에 필요한 코드를 생성합니다.  
  
 제대로 작동과 같은 순서로 지정 된 속성 페이지가 표시 됩니다는 `PROP_PAGE` 속성 맵에 있습니다. 일반적으로 넣어야 표준 속성 페이지 항목 엔트리 속성 맵에 지정 페이지에 대 한 사용자가 컨트롤에 관련 된 페이지를 먼저 표시 되도록 합니다.  
  
## <a name="example"></a>예  
 컨트롤이 사용 하는 일정에 대 한 다음 클래스는 **ISpecifyPropertyPages** 인터페이스를 사용자 지정 날짜 및 색상 스톡 페이지가 사용 하 여 해당 속성을 설정할 수 있는 컨테이너를 설명 합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../visual-cpp-samples.md)

