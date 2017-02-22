---
title: "CComSafeArrayBound Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComSafeArrayBound"
  - "ATL::CComSafeArrayBound"
  - "CComSafeArrayBound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSafeArrayBound class"
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComSafeArrayBound Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는  [SAFEARRAYBOUND](http://msdn.microsoft.com/ko-kr/303a9bdb-71d6-4f14-8747-84cf84936c6d) 구조.  
  
## 구문  
  
```  
  
class CComSafeArrayBound : public SAFEARRAYBOUND  
  
```  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[CComSafeArrayBound](../Topic/CComSafeArrayBound::CComSafeArrayBound.md)|생성자입니다.|  
|[GetCount](../Topic/CComSafeArrayBound::GetCount.md)|요소의 개수를 반환 하려면이 메서드를 호출 합니다.|  
|[GetLowerBound](../Topic/CComSafeArrayBound::GetLowerBound.md)|하한값을 반환 하도록이 메서드를 호출 합니다.|  
|[GetUpperBound](../Topic/CComSafeArrayBound::GetUpperBound.md)|상위 바운드를 반환 하려면이 메서드를 호출 합니다.|  
|[SetCount](../Topic/CComSafeArrayBound::SetCount.md)|요소 수를 설정 하려면이 메서드를 호출 합니다.|  
|[SetLowerBound](../Topic/CComSafeArrayBound::SetLowerBound.md)|하한값을 설정 하려면이 메서드를 호출 합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/CComSafeArrayBound::operator%20=.md)|집합의 `CComSafeArrayBound` 새 값입니다.|  
  
## 설명  
 이 클래스에 대 한 래퍼 되는  **SAFEARRAYBOUND** 구조를 사용 하 여  [CComSafeArray](../../atl/reference/ccomsafearray-class.md).  쿼리 및 단일 차원의 상한 및 하 한 범위 설정에 대 한 메서드를 제공 된 `CComSafeArray` 개체 및 포함 된 요소 수입니다.  다차원 `CComSafeArray` 개체의 배열을 사용 하 여 `CComSafeArrayBound` 개체, 각 차원에 대 한.  따라서 같은 메서드를 사용할 때  [GetCount](../Topic/CComSafeArrayBound::GetCount.md)에서이 메서드는 다차원 배열에서 요소 총 반환 한다는 주의.  
  
 **헤더:** atlsafe.h  
  
## 요구 사항  
 **헤더:** atlsafe.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)