---
title: "CFileTimeSpan Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileTimeSpan"
  - "ATL.CFileTimeSpan"
  - "ATL::CFileTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTimeSpan class"
  - "shared classes, CFileTimeSpan"
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTimeSpan Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 상대 날짜 및 시간 값을 파일에 연결을 관리 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
class CFileTimeSpan  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CFileTimeSpan::CFileTimeSpan](../Topic/CFileTimeSpan::CFileTimeSpan.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CFileTimeSpan::GetTimeSpan](../Topic/CFileTimeSpan::GetTimeSpan.md)|시간 범위에서 검색 하려면이 메서드를 호출 하 여 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::SetTimeSpan](../Topic/CFileTimeSpan::SetTimeSpan.md)|시간 범위를 설정 하려면이 메서드를 호출 하 여 `CFileTimeSpan` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CFileTimeSpan::operator \-](../Topic/CFileTimeSpan::operator%20-.md)|빼기를 수행에 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::operator \!\=](../Topic/CFileTimeSpan::operator%20!=.md)|두 `CFileTimeSpan` 개체가 다른지 비교합니다.|  
|[CFileTimeSpan::operator \+](../Topic/CFileTimeSpan::operator%20+.md)|더하기를 수행에 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::operator \+\=](../Topic/CFileTimeSpan::operator%20+=.md)|더하기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|  
|[CFileTimeSpan::operator \<](../Topic/CFileTimeSpan::operator%20%3C.md)|두 비교 `CFileTimeSpan` 개체는 하 급 결정 합니다.|  
|[CFileTimeSpan::operator \<\=](../Topic/CFileTimeSpan::operator%20%3C=.md)|두 비교 `CFileTimeSpan` 같음 또는 급을 결정 하는 개체입니다.|  
|[CFileTimeSpan::operator \=](../Topic/CFileTimeSpan::operator%20=.md)|할당 연산자입니다.|  
|[CFileTimeSpan::operator \-\=](../Topic/CFileTimeSpan::operator%20-=.md)|빼기를 수행는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|  
|[CFileTimeSpan::operator \=\=](../Topic/CFileTimeSpan::operator%20==.md)|두 `CFileTimeSpan` 개체가 같은지 비교합니다.|  
|[CFileTimeSpan::operator \>](../Topic/CFileTimeSpan::operator%20%3E.md)|두 비교 `CFileTimeSpan` 개체를 더 큰 결정 합니다.|  
|[CFileTimeSpan::operator \>\=](../Topic/CFileTimeSpan::operator%20%3E=.md)|두 비교 `CFileTimeSpan` 동등 하거나 더 큰 결정 하는 개체입니다.|  
  
## 설명  
 이 클래스 상대 기간을 관리 하기 위한 메서드를 제공 합니다. 시기와 관련 된 작업을 수행할 때 자주 발생 하는 시간을 파일 작성, 마지막 액세스 또는 마지막으로 수정 합니다.  이 클래스의 메서드를 함께에서 자주 사용 되는  [CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md) 개체입니다.  
  
## 예제  
 예제를 보려면  [CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md).  
  
## 요구 사항  
 **헤더:** atltime.h  
  
## 참고 항목  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime Class](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)