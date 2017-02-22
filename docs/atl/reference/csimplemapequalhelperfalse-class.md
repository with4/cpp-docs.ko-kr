---
title: "CSimpleMapEqualHelperFalse Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleMapEqualHelperFalse"
  - "CSimpleMapEqualHelperFalse"
  - "ATL.CSimpleMapEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelperFalse class"
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleMapEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 도우미에 대 한 것은  [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스.  
  
## 구문  
  
```  
  
template < class TKey, class TVal > class CSimpleMapEqualHelperFalse  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](../Topic/CSimpleMapEqualHelperFalse::IsEqualKey.md)|\(정적\) 두 키가 같은지 테스트합니다.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](../Topic/CSimpleMapEqualHelperFalse::IsEqualValue.md)|\(정적\) False를 반환 합니다.|  
  
## 설명  
 이 특성 클래스인 보완 하는 `CSimpleMap` 클래스입니다.  포함 된 두 요소를 비교 하는 메서드를 제공 합니다.는 `CSimpleMap` 개체, 특히 두 값 요소 또는 두 가지 핵심 요소입니다.  
  
 값 비교 항상 false를 반환 하 고 호출 또한 `ATLASSERT` 가 참조 하는 경우 false 인수를.  위치 같음 테스트 충분히 정의 되지 상황에서이 클래스에 대 한 대부분의 메서드는 제대로 작동 하지만 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식으로 실패할 수 있는 키\/값 쌍을 포함 하는 맵 있습니다  [CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md).  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 참고 항목  
 [CSimpleMapEqualHelper Class](../../atl/reference/csimplemapequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)