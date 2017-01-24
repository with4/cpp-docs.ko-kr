---
title: "Specifying Property Pages | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISpecifyPropertyPages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISpecifyPropertyPages method"
  - "속성 페이지, 지정"
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Specifying Property Pages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤을 만들 때 컨트롤의 속성을 설정 하는 데 사용할 수 있는 속성 페이지를 연결 하는 경우가 종종 있습니다.  컨트롤 컨테이너 사용을  **ISpecifyPropertyPages** 인터페이스 속성 페이지에서 컨트롤의 속성을 설정 하려면 사용할 수 있습니다 아웃을 찾으려면.  컨트롤에서이 인터페이스를 구현 해야 합니다.  
  
 구현 하기  **ISpecifyPropertyPages** ATL을 사용 하 여 다음 단계를 수행 하십시오.  
  
1.  파생 클래스에서  [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  항목에 대 한 추가  **ISpecifyPropertyPages** 클래스의 COM 맵에.  
  
3.  추가 된  [PROP\_PAGE](../Topic/PROP_PAGE.md) 항목을 컨트롤에 연결 된 각 페이지에 대 한 속성 맵에.  
  
> [!NOTE]
>  사용 하 여 표준 컨트롤을 생성할 때의  [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)만 추가 해야 합니다의 `PROP_PAGE` 속성 맵에 항목.  마법사의 다른 단계에 필요한 코드를 생성합니다.  
  
 제대로 작동에서 같은 순서로 지정 된 속성 페이지 표시 됩니다의 `PROP_PAGE` 속성 맵에.  사용자 컨트롤을 특정 페이지를 먼저 볼 수 있도록 일반적으로 하면 표준 속성 페이지 항목 항목 뒤 속성 맵에서 사용자 지정 페이지에 대해 설정 해야 합니다.  
  
## 예제  
 다음 클래스는 일정에 대 한 사용 제어는  **ISpecifyPropertyPages** 스톡 색 페이지 및 사용자 지정 날짜 페이지를 사용 하 여 속성을 설정할 수 컨테이너를 구별 하는 인터페이스입니다.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/CPP/specifying-property-pages_1.h)]  
  
## 참고 항목  
 [속성 페이지](../atl/atl-com-property-pages.md)   
 [ATLPages 샘플](../top/visual-cpp-samples.md)