---
title: "CFileTime Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CFileTime"
  - "CFileTime"
  - "ATL.CFileTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTime class"
  - "shared classes, CFileTime"
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에는 파일과 관련 된 날짜 및 시간 값을 관리 하는 방법을 제공 합니다.  
  
## 구문  
  
```  
  
   class CFileTime :   
public FILETIME  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CFileTime::CFileTime](../Topic/CFileTime::CFileTime.md)|생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CFileTime::GetCurrentTime](../Topic/CFileTime::GetCurrentTime.md)|검색이 정적 함수를 호출 하는 `CFileTime` 현재 시스템 날짜와 시간을 나타내는 개체입니다.|  
|[CFileTime::GetTime](../Topic/CFileTime::GetTime.md)|시간을 검색 하도록이 메서드를 호출 하는 `CFileTime` 개체입니다.|  
|[CFileTime::LocalToUTC](../Topic/CFileTime::LocalToUTC.md)|로컬 파일 시간에서 협정 세계시 \(UTC\)를 기준으로 파일 시간 변환 하려면이 메서드를 호출 합니다.|  
|[CFileTime::SetTime](../Topic/CFileTime::SetTime.md)|설정 날짜와 시간으로 저장 하려면이 메서드를 호출 하 여 `CFileTime` 개체입니다.|  
|[CFileTime::UTCToLocal](../Topic/CFileTime::UTCToLocal.md)|시간에서 협정 세계시 \(UTC\) 로컬 파일 시간을 기반으로 변환 하려면이 메서드를 호출 합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CFileTime::operator \-](../Topic/CFileTime::operator%20-.md)|이 연산자를 사용할에 빼기를 수행 하는 `CFileTime` 또는 `CFileTimeSpan` 개체.|  
|[CFileTime::operator \!\=](../Topic/CFileTime::operator%20!=.md)|이 연산자는 두 비교 `CFileTime` 개체에 대 한 같지 않음.|  
|[CFileTime::operator \+](../Topic/CFileTime::operator%20+.md)|이 연산자를 사용할에 더하기를 수행 하는 `CFileTimeSpan` 개체입니다.|  
|[CFileTime::operator \+\=](../Topic/CFileTime::operator%20+=.md)|이 연산자를 사용할에 더하기를 수행 하는 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당.|  
|[CFileTime::operator \<](../Topic/CFileTime::operator%20%3C.md)|이 연산자는 두 비교 `CFileTime` 개체는 하 급 결정 합니다.|  
|[CFileTime::operator \<\=](../Topic/CFileTime::operator%20%3C=.md)|이 연산자는 두 비교 `CFileTime` 같음 또는 급을 결정 하는 개체입니다.|  
|[CFileTime::operator \=](../Topic/CFileTime::operator%20=.md)|할당 연산자입니다.|  
|[CFileTime::operator \-\=](../Topic/CFileTime::operator%20-=.md)|빼기를 수행 하려면이 연산자를 사용할에 `CFileTimeSpan` 개체 및 현재 개체에 결과 할당 합니다.|  
|[CFileTime::operator \=\=](../Topic/CFileTime::operator%20==.md)|이 연산자는 두 비교 `CFileTime` 개체가 같은지.|  
|[CFileTime::operator \>](../Topic/CFileTime::operator%20%3E.md)|이 연산자는 두 비교 `CFileTime` 개체를 더 큰 결정 합니다.|  
|[CFileTime::operator \>\=](../Topic/CFileTime::operator%20%3E=.md)|이 연산자는 두 비교 `CFileTime` 동등 하거나 더 큰 결정 하는 개체입니다.|  
  
### 공용 상수  
  
|이름|설명|  
|--------|--------|  
|[CFileTime::Day](../Topic/CFileTime::Day.md)|100 나노초 간격의 숫자를 저장 하는 정적 데이터 멤버는 하루를 확인 합니다.|  
|[CFileTime::Hour](../Topic/CFileTime::Hour.md)|정적 데이터 멤버가 확인 한 시간을 100 나노초 간격의 수를 저장 합니다.|  
|[CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)|한 밀리초를 확인 하는 100 나노초 간격의 수를 저장 정적 데이터 멤버입니다.|  
|[CFileTime::Minute](../Topic/CFileTime::Minute.md)|정적 데이터 멤버는 1 분을 100 나노초 간격의 수를 저장 합니다.|  
|[CFileTime::Second](../Topic/CFileTime::Second.md)|정적 데이터 멤버는 1 초를 100 나노초 간격의 수를 저장 합니다.|  
|[CFileTime::Week](../Topic/CFileTime::Week.md)|100 나노초 간격의 숫자를 저장 하는 정적 데이터 멤버는 일주일을 확인 합니다.|  
  
## 설명  
 이 클래스는 날짜 및 시간 값을 작성, 액세스 및 수정 하는 파일의 연결을 관리 하는 방법을 제공 합니다.  메서드와이 클래스의 데이터는 자주 함께 사용 된 `CFileTimeSpan` 상대 시간 값을 처리 하는 개체입니다.  
  
 1601 년 1 월 1, 이후 100 나노초 간격의 수를 나타내는 64 비트 값으로 날짜 및 시간 값이 저장 됩니다.  이 협정 세계시 \(UTC\) 형식입니다.  
  
 다음 정적 const 멤버 변수 계산을 단순화 하기 위해 제공 됩니다.  
  
|멤버 변수|100 나노초 간격의 수|  
|-----------|-------------------|  
|Millisecond|10,000|  
|초|밀리초 \* 1000|  
|분|두 번째 \* 60|  
|시간|분 \* 60|  
|일|시간 \* 24|  
|주|일 \* 7|  
  
 **참고**  만들기 모든 파일 시스템을 기록할 수 있습니다 및 마지막 액세스 시간 및 일부 파일 시스템 기록을 동일한 방식으로.  예제는 Windows NT FAT 파일 시스템 만들기에 대 한 시간 10 밀리초의 해상도, 쓰기 시간 해상도 2 초가 있고 액세스 시간 해상도 1 일 \(액세스 날짜\) 있습니다.  NTFS에서 액세스 시간 1 시간 해상도 있습니다.  또한 FAT 디스크에서 시간을 현지 시간으로 기록 하지만 NTFS 디스크에서 시간을 UTC에 기록 합니다.  자세한 내용은  [파일 시간](http://msdn.microsoft.com/library/windows/desktop/ms724290).  
  
## 상속 계층 구조  
 `FILETIME`  
  
 `CFileTime`  
  
## 요구 사항  
 **헤더:** atltime.h  
  
## 참고 항목  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan Class](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)