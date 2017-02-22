---
title: "Aggregation | Microsoft Docs"
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
  - "aggregate objects [C++]"
  - "aggregation [C++]"
ms.assetid: 7125bb8e-b269-4b50-9bba-295b467a54cc
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Aggregation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

때 개체의 구현자로 미리 빌드된 다른 개체가 제공 하는 서비스를 이용 하려는 경우가 있습니다.  또한이 두 번째 개체를 첫 번째 자연 스러운 부분으로 표시 하 려 합니다.  모두 COM 달성 포함과 집합체를 통해 이러한 목표입니다.  
  
 집계 \(외부\) 포함 하는 개체 생성 과정의 일부로 포함 된 내부 개체를 만드는 내부 개체의 인터페이스는 외부에서 노출 된 있음을 의미 합니다.  개체 자체 또는 집계 가능한 수 있습니다.  되어 있으면 제대로 작동 하려면 집계에 대 한 특정 규칙을 따라야 합니다.  
  
 기본적으로, 모든  **IUnknown** 메서드 호출에 포함 된 개체를 포함 하는 개체에 위임 해야 합니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [Reusing Objects](http://msdn.microsoft.com/library/windows/desktop/ms678443)