---
title: "ATL 프로젝트의 COM+ 1.0 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.MTS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, COM+ 1.0 지원"
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL 프로젝트의 COM+ 1.0 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ATL 프로젝트 마법사](../../atl/reference/creating-an-atl-project.md)를 사용하여 COM\+ 1.0 구성 요소를 기본적으로 지원하는 프로젝트를 만들 수 있습니다.  
  
 COM\+ 1.0은 분산된 구성 요소 기반 응용 프로그램을 개발하도록 설계된 것입니다.  또한 이러한 응용 프로그램을 배포하고 관리하기 위한 런타임 인프라를 제공합니다.  
  
 **COM\+ 1.0 지원** 확인란을 선택하면 연결 단계에서 빌드 스크립트가 수정됩니다.  COM\+ 1.0 프로젝트는 다음과 같은 라이브러리에 연결됩니다.  
  
-   comsvcs.lib  
  
-   Mtxguid.lib  
  
 **COM\+ 1.0 지원** 확인란을 선택하면 **구성 요소 등록자 지원**도 선택할 수 있습니다.  구성 요소 등록자를 사용하면 COM\+ 1.0 개체는 구성 요소 목록을 얻거나, 개별적으로 또는 한꺼번에 구성 요소를 등록하거나 등록 취소할 수 있습니다.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL 및 C 런타임 코드를 사용한 프로그래밍](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [기본 ATL 프로젝트 구성](../../atl/reference/default-atl-project-configurations.md)