---
title: "CTime Class | Microsoft Docs"
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
  - "ATL.CTime"
  - "CTime"
  - "ATL::CTime"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTime class"
  - "shared classes, CTime"
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTime Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

절대 시간과 날짜를 나타냅니다.  
  
## 구문  
  
```  
class CTime  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CTime::CTime](../Topic/CTime::CTime.md)|생성 `CTime` 개체에서 다양 한 방법으로.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CTime::Format](../Topic/CTime::Format.md)|변환는 `CTime` 개체를 서식이 지정 된 문자열\-현지 표준 시간대를 기반으로 합니다.|  
|[CTime::FormatGmt](../Topic/CTime::FormatGmt.md)|변환에 `CTime` 개체를 서식이 지정 된 문자열\-UTC를 기준으로 합니다.|  
|[CTime::GetAsDBTIMESTAMP](../Topic/CTime::GetAsDBTIMESTAMP.md)|변환 저장 된 시간 정보는 `CTime` 개체에 Win32 호환 <xref:System.Data.OleDb.OleDbType> 구조.|  
|[CTime::GetAsSystemTime](../Topic/CTime::GetAsSystemTime.md)|변환 저장 된 시간 정보는 `CTime` 개체에 Win32 호환  [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조.|  
|[CTime::GetCurrentTime](../Topic/CTime::GetCurrentTime.md)|생성 한 `CTime` \(정적 멤버 함수\) 현재 시간을 나타내는 개체.|  
|[CTime::GetDay](../Topic/CTime::GetDay.md)|가 날 나타내는 반환 된 `CTime` 개체.|  
|[CTime::GetDayOfWeek](../Topic/CTime::GetDayOfWeek.md)|나타내는 요일 반환의 `CTime` 개체입니다.|  
|[CTime::GetGmtTm](../Topic/CTime::GetGmtTm.md)|분류는 `CTime` 개체에 구성 요소\-UTC를 기준으로 합니다.|  
|[CTime::GetHour](../Topic/CTime::GetHour.md)|표시 되는 시간 반환 된 `CTime` 개체.|  
|[CTime::GetLocalTm](../Topic/CTime::GetLocalTm.md)|분류는 `CTime` 개체에 구성 요소\-현지 표준 시간대를 기준으로 합니다.|  
|[CTime::GetMinute](../Topic/CTime::GetMinute.md)|분을 나타내는 반환의 `CTime` 개체.|  
|[CTime::GetMonth](../Topic/CTime::GetMonth.md)|월 반환 된 `CTime` 개체입니다.|  
|[CTime::GetSecond](../Topic/CTime::GetSecond.md)|표시 되 고 두 번째 반환의 `CTime` 개체입니다.|  
|[CTime::GetTime](../Topic/CTime::GetTime.md)|반환은  **\_\_time64\_t** 값에 지정 된 `CTime` 개체.|  
|[CTime::GetYear](../Topic/CTime::GetYear.md)|표시 되는 연도 반환 된 `CTime` 개체입니다.|  
|[CTime::Serialize64](../Topic/CTime::Serialize64.md)|보관 파일에서 데이터를 serialize합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \+\-](../Topic/CTime::operator%20+,%20-.md)|이러한 연산자는 더하기 및 빼기 `CTimeSpan` 및 `CTime` 개체입니다.|  
|[연산자 \+ \=, \=](../Topic/CTime::operator%20+=,%20-=.md)|이러한 연산자는 더하기 및 빼기를 `CTimeSpan` 개체와이 `CTime` 개체입니다.|  
|[연산자 \=](../Topic/CTime::operator%20=.md)|할당 연산자입니다.|  
|[연산자: \= \=, \< 등.](../Topic/CTime%20Comparison%20Operators.md)|비교 연산자입니다.|  
  
## 설명  
 `CTime`기본 클래스에 없는 것입니다.  
  
 `CTime`값 협정 세계시에 UTC 협정 세계시로 \(GMT, 그리니치 표준시\)에 해당 하는 기반으로 합니다.  참조 [시간 관리](../../c-runtime-library/time-management.md) 에 대 한 표준 시간대를 확인 하는 방법에 대 한 정보.  
  
 만들 때에 `CTime` 개체, 설정 된 `nDST` 매개 변수는 표준 시간을 나타내는 0이 적용, 또는 나타내려면 0 보다 큰 값으로는 일광 절약 시간이 적용 되 나 C 런타임 라이브러리 코드 계산에 0 보다 작은 값 여부 표준 시간이 나 일광 절약 시간이 적용 되.  `tm_isdst`필수 필드가입니다.  설정 하지 값은 정의 되어 있지 않은지와 반환 값을  [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 예측할 수 없습니다.  경우 `timeptr` 이전 호출에 의해 반환 된 tm 구조체를 가리키는  [asctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md),  [\_gmtime\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), 또는  [localtime\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` 필드가 올바른 값을 포함 합니다.  
  
 도우미 클래스를  [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), 시간 간격을 나타냅니다.  
  
 `CTime` 및 `CTimeSpan` 클래스 파생에 대 한 설계 되지 않았습니다.  가상 함수가 없는 크기 때문에 `CTime` 및 `CTimeSpan` 개체는 정확히 8 바이트입니다.  대부분의 멤버 함수를 인라인 됩니다.  
  
> [!NOTE]
>  위 날짜 제한 12\/31\/3000입니다.  하한값입니다 1970\/1\/1 12시: 00 AM GMT입니다.  
  
 사용에 대 한 자세한 내용은 `CTime`, 문서를 참조 하십시오.  [날짜와 시간](../../atl-mfc-shared/date-and-time.md), 및  [시간 관리](../../c-runtime-library/time-management.md) 런타임 라이브러리 참조에서.  
  
> [!NOTE]
>  `CTime` 구조에 MFC 8.0에서 MFC 7.1 변경 합니다.  Serialize 하는 경우는 `CTime` 를 사용 하 여 구조는 `operator <<` MFC 8.0 이상 버전에서 파일 결과 이전 버전의 MFC에서 읽을 수 없습니다.  
  
## 요구 사항  
 **헤더:** atltime.h  
  
## 참고 항목  
 [asctime\_s, \_wasctime\_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [\_ftime\_s, \_ftime32\_s, \_ftime64\_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime\_s, \_gmtime32\_s, \_gmtime64\_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime\_s, \_localtime32\_s, \_localtime64\_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, \_strftime\_l, \_wcsftime\_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, \_time32, \_time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan Class](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)