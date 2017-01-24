---
title: "CDefaultHashTraits Class | Microsoft Docs"
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
  - "CDefaultHashTraits"
  - "ATL.CDefaultHashTraits<T>"
  - "ATL::CDefaultHashTraits<T>"
  - "ATL.CDefaultHashTraits"
  - "ATL::CDefaultHashTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultHashTraits class"
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultHashTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 해시 값을 계산 하는 정적 함수를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   typename T  
>  
class CDefaultHashTraits  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDefaultHashTraits::Hash](../Topic/CDefaultHashTraits::Hash.md)|\(정적\) 지정 된 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.|  
  
## 설명  
 이 클래스는 지정 된 요소에 대 한 해시 값을 반환 하는 단일 정적 함수를 포함 합니다.  이 클래스에서 활용 되는  [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md).  
  
 자세한 내용은  [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)