---
title: "CTimeSpan 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5c76411f6c1302d406b07cc79d9c544e3ad8c43b
ms.lasthandoff: 02/24/2017

---
# <a name="ctimespan-class"></a>CTimeSpan 클래스
내부적으로 시간 범위에서 수 시간 (초)으로 저장 되는 시간 만큼 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|생성 `CTimeSpan` 다양 한 방법으로 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|변환 된 `CTimeSpan` 서식이 지정 된 문자열에 있습니다.|  
|[CTimeSpan::GetDays](#getdays)|두 일 수를 나타내는 값을 반환 `CTimeSpan`합니다.|  
|[CTimeSpan::GetHours](#gethours)|현재 날짜 (–23부터 23까지)의 시간 수를 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetMinutes](#getminutes)|(–59부터 59까지)는 현재 시간에서 분 수를 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetSeconds](#getseconds)|(–59부터 59까지)는 현재 분의 초 수를 나타내는 값을 반환 합니다.|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|값을 반환 된 `CTimeSpan` 개체입니다.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|이 전체 시간의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|이 분의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|이 경과 된 초의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.|  
|[CTimeSpan::Serialize64](#serialize64)|보관 파일에서 데이터를 serialize합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 +-](#operator_add_-)|추가 하 고 뺍니다 `CTimeSpan` 개체입니다.|  
|[operator + = – =](#operator_add_eq_-_eq)|추가 하 고 뺍니다는 `CTimeSpan` 개체와이 `CTimeSpan`합니다.|  
|[연산자 = =<>](#ctimespan_comparison_operators)|두 개의 상대 시간 값을 비교합니다.|  
  
## <a name="remarks"></a>주의  
 `CTimeSpan`기본 클래스는 없습니다.  
  
 `CTimeSpan`함수는 다양 한 일, 시간, 분, 초 및 시간 (초)을 변환합니다.  
  
 `CTimeSpan` 개체에 저장 되어는 **__time64_t** 구조체에는 8 바이트입니다.  
  
 도우미 클래스가 [CTime](../../atl-mfc-shared/reference/ctime-class.md), 절대 시간을 나타냅니다.  
  
 `CTime` 및 `CTimeSpan` 클래스는 파생을 위한 설계 되지 않았습니다. 가상 함수를 둘 다의 크기 때문에 `CTime` 및 `CTimeSpan` 개체는 8 바이트 정확 하 게 합니다. 대부분의 멤버 함수는 인라인으로 됩니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTimeSpan`, 문서를 참조 [날짜 및 시간](../../atl-mfc-shared/date-and-time.md), 및 [시간 관리](../../c-runtime-library/time-management.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>CTimeSpan 비교 연산자  
 비교 연산자입니다.  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
  
 비교할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이러한 연산자는 두 개의 상대 시간 값을 비교합니다. 반환 **true** 조건이 true이 고, 그렇지 않으면 **false**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&169;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 생성 `CTimeSpan` 다양 한 방법으로 개체입니다.  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *timeSpanSrc*  
 A `CTimeSpan` 이미 있는 개체입니다.  
  
 `time`  
 A **__time64_t** 시간 값을 시간 범위에서의 시간 (초)입니다. Visual c + + 버전 6.0 및 이전 버전에서 `time` 의 값이 `time_t`합니다. Visual c + +.NET 나중에 자동으로 변환 하거나 한 `time_t` 매개 변수를 **__time64_t**합니다.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 일, 시간, 분 및 초를 각각.  
  
### <a name="remarks"></a>주의  
 이러한 모든 생성자는 새 만들 `CTimeSpan` 개체가 지정된 된 상대 시간으로 초기화 합니다. 다음은 각 생성자에 대 한 설명입니다.  
  
- **CTimeSpan (); ** 초기화 되지 않은 생성 `CTimeSpan` 개체입니다.  
  
- **CTimeSpan (const CTimeSpan / /); ** 생성 한 `CTimeSpan` 개체에서 다른 `CTimeSpan` 값입니다.  
  
- **CTimeSpan (__time64_t); ** 생성 한 `CTimeSpan` 에서 개체는 **__time64_t** 유형입니다.  
  
- **CTimeSpan (긴**, **int, int, int);** 생성 된 `CTimeSpan` 각 구성 요소와 구성 요소에서 개체는 다음 범위를 제한 합니다.  
  
    |구성 요소|범위|  
    |---------------|-----------|  
    |`lDays`|0-25,&000; (약)|  
    |`nHours`|0–23|  
    |`nMins`|0–59|  
    |`nSecs`|0–59|  
  
 시간 구성 요소 중 하나는 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션하는 이상의 범위를 벗어났습니다. 가 호출 하기 전에 인수의 유효성을 검사 해야 프로그램입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&162;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 이에 해당 하는 형식이 지정 된 문자열을 생성 `CTimeSpan`합니다.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pFormat`, `pszFormat`  
 유사한 문자열 서식는 `printf` 문자열의 형식을 지정 합니다. 형식 지정 코드를 앞에 백분율 ( `%`) 서명, 해당 바뀝니다 `CTimeSpan` 구성 요소입니다. 서식 문자열에 다른 문자는 반환 된 문자열에 변경 되지 않은 상태로 복사 됩니다. 값과에 대 한 서식 지정 코드의 의미 **형식** 아래와 같습니다.  
  
- **%D** 총 일이`CTimeSpan`  
  
- **%H** 은 현재 날짜 시간  
  
- **%M** 현재 시간의 분  
  
- **%S** 현재 분의 초  
  
- **%%**백분율 기호  
  
 `nID`  
 이 형식을 식별 하는 문자열의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 서식이 지정 된 시간을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 라이브러리의 디버그 버전 서식 지정 코드를 검사 하 고 코드는 위의 목록에 없으면 어설션 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&163;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 두 일 수를 나타내는 값을 반환 `CTimeSpan`합니다.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 시간 범위에서 전체 24 시간 일 수를 반환합니다. 이 값 시간 범위 음수인 경우에 음수가 될 수 있습니다.  
  
### <a name="remarks"></a>주의  
 일광 절약 시간을 일으킬 수 있는 참고 `GetDays` 잠재적으로 놀라운 결과를 반환 합니다. 예를 들어 DST 경우 실제로 **GetDays** 4 월에서 1 일 1 시간 단축 및 완료 일으로 계산 되지 않는 때문에 29, 30이 아닌으로 4 월 1 일에서 5 월 1 사이의 일 수를 보고 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&164;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 현재 날짜 (–23부터 23까지)의 시간 수를 나타내는 값을 반환 합니다.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 날짜에 시간을 반환합니다. 범위는-23 –23입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&165;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 (–59부터 59까지)는 현재 시간에서 분 수를 나타내는 값을 반환 합니다.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 시간에서 분 수를 반환합니다. 범위는-59 –59입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetHours](#gethours)합니다.  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 (–59부터 59까지)는 현재 분의 초 수를 나타내는 값을 반환 합니다.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 분의 초 수를 반환합니다. 범위는-59 –59입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetHours](#gethours)합니다.  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 값을 반환 된 `CTimeSpan` 개체입니다.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 값을 반환 된 `CTimeSpan` 개체입니다.  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 이 전체 시간의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 전체 시간의 총 수를 반환 합니다. `CTimeSpan`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&166; 증가](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 이 분의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 경과 된 분 총 수를 반환 합니다. `CTimeSpan`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetTotalHours](#gettotalhours)합니다.  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 이 경과 된 초의 총 수를 나타내는 값을 반환 `CTimeSpan`합니다.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 총 경과 된 초 수를 반환 합니다. `CTimeSpan`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetTotalHours](#gettotalhours)합니다.  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +,-  
 추가 하 고 뺍니다 `CTimeSpan` 개체입니다.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 에 추가할 값의 `CTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CTimeSpan` 작업의 결과 나타내는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이러한 두 연산자를 사용 하면 더하기 및 빼기 수 있도록 `CTimeSpan` 개체와 서로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&167;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator + =, =  
 추가 하 고 뺍니다는 `CTimeSpan` 개체와이 `CTimeSpan`합니다.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 에 추가할 값의 `CTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 `CTimeSpan` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이러한 연산자를 사용 하면 더하기 및 빼기 수 있도록는 `CTimeSpan` 개체와이 `CTimeSpan`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&168;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  이 메서드는 MFC 프로젝트에서 사용할 수만 있습니다.  
  
 멤버 변수를 또는 보관에서 연관 된 데이터를 serialize 합니다.  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 `ar`  
 `CArchive` 개체를 업데이트 하려면 선택 합니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 `CArchive` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)



