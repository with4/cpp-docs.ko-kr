---
title: "CDefaultCharTraits Class | Microsoft Docs"
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
  - "CDefaultCharTraits"
  - "ATL::CDefaultCharTraits<T>"
  - "ATL.CDefaultCharTraits"
  - "ATL.CDefaultCharTraits<T>"
  - "ATL::CDefaultCharTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCharTraits class"
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultCharTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 문자 대 \/ 소문자를 변환 하는 두 정적 함수를 제공 합니다.  
  
## 구문  
  
```  
  
      template <  
   typename T  
>  
class CDefaultCharTraits  
```  
  
#### 매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDefaultCharTraits::CharToLower](../Topic/CDefaultCharTraits::CharToLower.md)|\(정적\) 문자를 대문자로 변환 하려면이 함수를 호출 합니다.|  
|[CDefaultCharTraits::CharToUpper](../Topic/CDefaultCharTraits::CharToUpper.md)|\(정적\) 문자를 소문자로 변환 하려면이 함수를 호출 합니다.|  
  
## 설명  
 이 클래스는 클래스에 의해 사용 되는 기능 제공  [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
## 요구 사항  
 **헤더:** atlcoll.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)