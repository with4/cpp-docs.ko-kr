---
title: "CSimpleMapEqualHelper Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleMapEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelper class"
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSimpleMapEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 도우미에 대 한 것은  [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스.  
  
## 구문  
  
```  
  
      template <  
   class TKey,  
   class TVal   
>  
class CSimpleMapEqualHelper  
```  
  
#### 매개 변수  
 `TKey`  
 키 요소입니다.  
  
 `TVal`  
 값 요소입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleMapEqualHelper::IsEqualKey](../Topic/CSimpleMapEqualHelper::IsEqualKey.md)|\(정적\) 두 키가 같은지 테스트합니다.|  
|[CSimpleMapEqualHelper::IsEqualValue](../Topic/CSimpleMapEqualHelper::IsEqualValue.md)|\(정적\) 두 값이 같은지 테스트합니다.|  
  
## 설명  
 이 특성 클래스인 보완 하는 `CSimpleMap` 클래스입니다.  두 개를 비교 하는 메서드를 제공 합니다. `CSimpleMap` 개체 요소 \(특히, 키 및 값 구성\) 같은지.  기본적으로 키와 값을 사용 하 여 비교 하는 `operator==()`, 하지만이 클래스 필요한 추가 기능을 사용 하려면 지도 자신의 같음 연산자가 없는 복잡 한 데이터 형식이 포함 된 경우 재정의할 수 있습니다.  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 참고 항목  
 [CSimpleMapEqualHelperFalse Class](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)