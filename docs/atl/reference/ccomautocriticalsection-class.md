---
title: "CComAutoCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoCriticalSection"
  - "ATL::CComAutoCriticalSection"
  - "CComAutoCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoCriticalSection class"
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComAutoCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComAutoCriticalSection`구하고 중요 섹션 개체의 소유권을 해제에 대 한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CComAutoCriticalSection : public CComCriticalSection  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](../Topic/CComAutoCriticalSection::CComAutoCriticalSection.md)|생성자입니다.|  
|[CComAutoCriticalSection::~CComAutoCriticalSection](../Topic/CComAutoCriticalSection::~CComAutoCriticalSection.md)|소멸자|  
  
## 설명  
 `CComAutoCriticalSection`클래스와 비슷합니다  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)를 제외 하 고 `CComAutoCriticalSection` 자동으로 중요 섹션 개체의 생성자에서 초기화 합니다.  
  
 일반적으로 사용 `CComAutoCriticalSection` 통해는 `typedef` 이름  [AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md).  이 이름을 참조 `CComAutoCriticalSection` 때  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 사용 중입니다.  
  
 `Init` 및 `Term` 메서드에서  [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) 이 클래스를 사용 하는 경우에 사용할 수 없습니다.  
  
## 상속 계층 구조  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## 요구 사항  
 **헤더:**  atlcore.h  
  
## 참고 항목  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCriticalSection Class](../../atl/reference/ccomcriticalsection-class.md)