---
title: "CSimpleArrayEqualHelper Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleArrayEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelper class"
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleArrayEqualHelper Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 도우미에 대 한 것은  [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스.  
  
## 구문  
  
```  
  
      template <  
   class T   
>  
class CSimpleArrayEqualHelper  
```  
  
#### 매개 변수  
 `T`  
 파생 된 클래스입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSimpleArrayEqualHelper::IsEqual](../Topic/CSimpleArrayEqualHelper::IsEqual.md)|\(정적\) 두 테스트 `CSimpleArray` 개체 요소가 같은지.|  
  
## 설명  
 이 특성 클래스인 보완 하는 `CSimpleArray` 클래스입니다.  저장에서 두 요소를 비교 하는 방법을 제공 된 `CSimpleArray` 개체입니다.  기본적으로 요소를 사용 하 여 비교  **operator\=\(\)**, 하지만 배열 자신의 같음 연산자가 없는 복잡 한 데이터 형식이 포함 되어 있으면이 클래스를 재정의 해야 합니다.  
  
## 요구 사항  
 **헤더:** atlsimpcoll.h  
  
## 참고 항목  
 [CSimpleArray Class](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse Class](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)