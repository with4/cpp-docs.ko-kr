---
title: "CSimpleArrayEqualHelperFalse Class | Microsoft Docs"
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
  - "ATL.CSimpleArrayEqualHelperFalse<T>"
  - "ATL::CSimpleArrayEqualHelperFalse"
  - "ATL.CSimpleArrayEqualHelperFalse"
  - "ATL::CSimpleArrayEqualHelperFalse<T>"
  - "CSimpleArrayEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelperFalse class"
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleArrayEqualHelperFalse Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 도우미에 대 한 것은  [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스.  
  
## 구문  
  
```  
  
      template <  
   class T   
>   
class CSimpleArrayEqualHelperFalse  
```  
  
#### 매개 변수  
 `T`  
 파생 된 클래스입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](../Topic/CSimpleArrayEqualHelperFalse::IsEqual.md)|\(정적\) False를 반환 합니다.|  
  
## 설명  
 이 특성 클래스를 보완 하 되는 `CSimpleArray` 클래스입니다.  항상 it 반환 합니다 거짓을 하 고 또한 호출 `ATLASSERT` 가 참조 하는 경우 false는 인수.  위치 같음 테스트 충분히 정의 되지 상황에서이 클래스에 대 한 대부분의 메서드는 제대로 작동 하지만 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식으로 실패 하는 요소를 포함 하는 배열 수  [CSimpleArray::Find](../Topic/CSimpleArray::Find.md).  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 참고 항목  
 [CSimpleArrayEqualHelper Class](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)