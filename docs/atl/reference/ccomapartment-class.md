---
title: "CComApartment Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComApartment"
  - "CComApartment"
  - "ATL.CComApartment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "apartments in ATL EXE modules"
  - "CComApartment class"
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComApartment Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 appartment 스레드 풀링 EXE 모듈에서을 관리 하기 위한 기능을 지원 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CComApartment  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComApartment::CComApartment](../Topic/CComApartment::CComApartment.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComApartment::Apartment](../Topic/CComApartment::Apartment.md)|스레드의 시작 주소를 표시합니다.|  
|[CComApartment::GetLockCount](../Topic/CComApartment::GetLockCount.md)|스레드의 현재 잠금 수를 반환합니다.|  
|[CComApartment::Lock](../Topic/CComApartment::Lock.md)|스레드의 잠금 횟수를 늘립니다.|  
|[CComApartment::Unlock](../Topic/CComApartment::Unlock.md)|스레드의 잠금 횟수를 줄입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CComApartment::m\_dwThreadID](../Topic/CComApartment::m_dwThreadID.md)|스레드 식별자를 포함 합니다.|  
|[CComApartment::m\_hThread](../Topic/CComApartment::m_hThread.md)|스레드의 핸들을 포함 합니다.|  
|[CComApartment::m\_nLockCnt](../Topic/CComApartment::m_nLockCnt.md)|스레드의 현재 잠금 수가 있습니다.|  
  
## 설명  
 `CComApartment`사용 하 여  [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) 아파트 스레드 풀링 EXE 모듈에서 관리 합니다.  `CComApartment`증가 및 감소 된 잠금에 대 한 방법에서 스레드 개수를 제공 합니다.  
  
## 요구 사항  
 **헤더:**  atlbase.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)