---
title: CTime 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec195c7733255487b08f8b48379abe58e305f61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ctime-class"></a>CTime 클래스
절대 시간 및 날짜를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTime  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTime::CTime](#ctime)|생성 `CTime` 다양 한 방법으로 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTime::Format](#format)|변환는 `CTime` 서식이 지정 된 문자열에는 개체-현지 표준 시간대에 따라 합니다.|  
|[CTime::FormatGmt](#formatgmt)|변환는 `CTime` 서식이 지정 된 문자열에는 개체-UTC 기준입니다.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|변환에 저장 된 시간 정보는 `CTime` Win32 호환 DBTIMESTAMP 구조에는 개체입니다.|  
|[CTime::GetAsSystemTime](#getassystemtime)|변환에 저장 된 시간 정보는 `CTime` Win32 호환 되는 개체 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조입니다.|  
|[CTime::GetCurrentTime](#getcurrenttime)|만듭니다는 `CTime` (정적 멤버 함수)는 현재 시간을 나타내는 개체입니다.|  
|[CTime::GetDay](#getday)|의해 일 표시를 반환 합니다.는 `CTime` 개체입니다.|  
|[CTime::GetDayOfWeek](#getdayofweek)|나타내는 주의 일을 반환 된 `CTime` 개체입니다.|  
|[CTime::GetGmtTm](#getgmttm)|분할 하는 `CTime` 구성 요소에는 개체-UTC 기준입니다.|  
|[CTime::GetHour](#gethour)|가 나타내는 시간을 반환 합니다는 `CTime` 개체입니다.|  
|[CTime::GetLocalTm](#getlocaltm)|분할 하는 `CTime` 구성 요소에는 개체-현지 표준 시간대에 따라 합니다.|  
|[CTime::GetMinute](#getminute)|가 나타내는 분 단위는 `CTime` 개체입니다.|  
|[CTime::GetMonth](#getmonth)|가 나타내는 월 반환는 `CTime` 개체입니다.|  
|[CTime::GetSecond](#getsecond)|가 나타내는 두 번째 반환 된 `CTime` 개체입니다.|  
|[CTime::GetTime](#gettime)|반환은 **__time64_t** 에 대 한 값은 지정 된 `CTime` 개체입니다.|  
|[CTime::GetYear](#getyear)|가 나타내는 연도 반환 된 `CTime` 개체입니다.|  
|[CTime::Serialize64](#serialize64)|보관 파일에서 데이터를 serialize합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 +-](#operator_add_-)|이러한 연산자는 더하기 및 빼기 `CTimeSpan` 및 `CTime` 개체입니다.|  
|[operator + =, =](#operator_add_eq_-_eq)|이러한 연산자는 더하기 및 빼기는 `CTimeSpan` 개체와이 `CTime` 개체입니다.|  
|[operator =](#operator_eq)|대입 연산자입니다.|  
|[연산자 = =, <, 등입니다.](#ctime_comparison_operators)|비교 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 `CTime` 기본 클래스는 없습니다.  
  
 `CTime` 값은 기반으로 협정 세계시 (UTC) 협정 세계시 (그리니치 표준시, GMT)와 같습니다. 참조 [시간 관리](../../c-runtime-library/time-management.md) 표준 시간대를 결정 하는 방법에 대 한 정보에 대 한 합니다.  
  
 만들 때 한 `CTime` 개체, 설정 된 `nDST` 표준시 실제로 또는를 나타내는 0 보다 큰 값으로 해당 일광 절약 시간제가 적용 된 경우를 나타내기 위해 0으로 또는 C 런타임 라이브러리 코드 컴퓨터가 0 보다 작은 값으로 매개 변수 e 표준 시간 또는 일광 절약 시간제의 적용 중인지 여부. `tm_isdst`는 필수 필드입니다. 을 설정 하지 값 정의 되지 않습니다 및 반환 값을 [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 를 예측할 수 없습니다. 경우 `timeptr` 대 한 이전 호출에서 반환 되는 tm 구조체를 가리키는 [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), 또는 [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` 필드에는 올바른 값입니다.  
  
 도우미 클래스가 [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), 시간 간격을 나타냅니다.  
  
 `CTime` 및 `CTimeSpan` 클래스는 파생을 위해 설계 되지 않았습니다. 크기의 가상 함수가 없는 있기 때문에 `CTime` 및 `CTimeSpan` 개체는 8 바이트 정확 하 게 합니다. 대부분의 멤버 함수는 인라인으로 됩니다.  
  
> [!NOTE]
>  위쪽 날짜 제한은 12/31/3000입니다. 하 한은 1/1/1970 12시: 00 AM GMT입니다.  
  
 사용에 대 한 자세한 내용은 `CTime`, 문서를 참조 [날짜 및 시간](../../atl-mfc-shared/date-and-time.md), 및 [시간 관리](../../c-runtime-library/time-management.md) 런타임 라이브러리 참조에서.  
  
> [!NOTE]
>  `CTime` MFC 7.1에서 MFC 8.0로 변경 된 구조입니다. Serialize 하는 경우는 `CTime` 를 사용 하 여 구조는 `operator <<` MFC 8.0 또는 이후 버전에서는 결과 파일 됩니다 이전 버전의 MFC에서 읽을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>  CTime 비교 연산자  
 비교 연산자입니다.  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 `time`  
 비교할 `CTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이러한 연산자는 두 절대 시간을 비교 하 고 반환 **true** 조건이 true이 고, 그렇지 않으면 **false**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>  CTime::CTime  
 새 `CTime` 지정된 시간으로 초기화 하는 개체입니다.  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `timeSrc`  
 나타냅니다는 `CTime` 이미 있는 개체입니다.  
  
 `time`  
 A **__time64_t** 시간 값을 UTC 1970 년 1 월 1 일 이후 시간 (초)입니다. 현지 시간으로 조정 됩니다이 note 합니다. 예를 들어, 뉴욕에 있고 만들기는 `CTime` 0을 매개 변수를 전달 하 여 [CTime::GetMonth](#getmonth) 12를 반환 합니다.  

  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 복사할 새 날짜 및 시간 값을 나타내는 `CTime` 개체입니다.  
  
 `nDST`  
 일광 절약 시간이 적용 되어 있는지 여부를 나타냅니다. 세 값 중 하나를 가질 수 있습니다.  
  
- `nDST` 0Standard 시간으로 설정 적용 됩니다.  
  
- `nDST` 값으로 설정 절약 시간이 적용 중인 0Daylight 보다 큽니다.  
  
- `nDST` 0The 기본값 보다 작은 값으로 설정 합니다. 표준 시간 또는 일광 절약 시간이 적용 중인지 여부를 자동으로 계산 합니다.  
  
 `wDosDate`, `wDosTime`  
 날짜/시간 값으로 변환 하 고 새 복사 MS-DOS 날짜 및 시간 값 `CTime` 개체입니다.  
  
 `st`  
 A [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) 날짜/시간 값으로 변환 하 고 새 복사 구조 `CTime` 개체입니다.  
  
 `ft`  
 A [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) 날짜/시간 값으로 변환 하 고 새 복사 구조 `CTime` 개체입니다.  
  
 dbts  
 현재 현지 시간을 포함 하는 DBTIMESTAMP 구조체에 대 한 참조입니다.  
  
### <a name="remarks"></a>설명  
 다음은 각 생성자에 대 한 설명입니다.  
  
- **CTime();**  초기화 되지 않은 생성 `CTime` 개체입니다. 이 생성자를 정의할 수 있습니다 `CTime` 배열 개체입니다. 이러한 배열을 사용 하기 전에 유효한 시간으로 초기화 해야 합니다.  
  
- **CTime (const CTime & a);**  생성 한 `CTime` 개체에서 다른 `CTime` 값입니다.  
  
- **CTime (__time64_t);**  생성 한 `CTime` 에서 개체는 **__time64_t** 유형입니다. 이 생성자는 UTC 시간을 예상 하 고 결과 저장 하기 전에 결과 현지 시간으로 변환 합니다.  
  
- **CTime (int, int,...);**  생성 한 `CTime` 각 구성 요소와 현지 시간 구성 요소에서 개체는 다음 범위를 제한 합니다.  
  
    |구성 요소|범위|  
    |---------------|-----------|  
    |`nYear`|1970-3000|  
    |`nMonth`|1-12|  
    |`nDay`|1-31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     이 생성자에는 UTC로 적절 한 변환을 수행 합니다. Microsoft Foundation Class 라이브러리의 디버그 버전 하나 하면 어설션 또는 시간 구성 요소 범위를 벗어났습니다. 호출 하기 전에 인수를 확인 해야 합니다. 이 생성자는 현지 시간을 예상합니다.  
  
- **CTime (WORD, 단어);**  생성 한 `CTime` 개체는 지정 된 MS-DOS 날짜 및 시간 값에서입니다. 이 생성자는 현지 시간을 예상합니다.  
  
- **CTime (const SYSTEMTIME & a);**  생성 한 `CTime` 에서 개체는 `SYSTEMTIME` 구조입니다. 이 생성자는 현지 시간을 예상합니다.  
  
- **CTime (const FILETIME & a);**  생성 한 `CTime` 에서 개체는 `FILETIME` 구조입니다. 경우는 거의 사용 하지 것입니다 `CTime FILETIME` 직접 초기화 합니다. 사용 하는 경우는 `CFile` 파일을 조작 하는 개체 `CFile::GetStatus` 를 통해 파일 타임 스탬프를 검색 한 `CTime` 사용 하 여 개체 초기화는 `FILETIME` 구조입니다. 이 생성자는 시간을 UTC 기준으로 간주 하 고 자동으로 해당 결과 저장 하기 전에 값을 현지 시간 변환 합니다.  
  
    > [!NOTE]
    >  사용 하 여 생성자 **DBTIMESTAMP** OLEDB.h 포함 되는 경우에 매개 변수는 사용할 수만 있습니다.  
  
 자세한 내용은 참조는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 및 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK에는 구조입니다. 또한 참조는 [MS-DOS 날짜 및 시간](http://msdn.microsoft.com/library/windows/desktop/ms724503) Windows SDK에는 항목입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>  CTime::Format  
 날짜 및 시간 값의 서식이 지정 된 표현을 만드는 데이 함수를 호출 합니다.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>매개 변수  
 `pszFormat`  
 유사한 문자열 서식는 `printf` 문자열의 서식을 지정 합니다. 형식 지정 코드를 앞에 백분율 ( `%`) 로그인을 하면 해당 대체 `CTime` 구성 요소입니다. 서식 문자열에 다른 문자는 반환 된 문자열에 변경 되지 않고 복사 됩니다. 런타임 함수를 참조 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 형식 지정 코드의 목록에 대 한 합니다.  
  
 `nFormatID`  
 이 형식을 식별 하는 문자열의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 서식이 지정 된 시간을 포함 하는 합니다.  
  
### <a name="remarks"></a>설명  
 경우이 상태의 `CTime` 개체 null 이면 반환 값은 빈 문자열입니다.  
  
 이 메서드는 3000 년 12 월 31 일을 통해 1970 년 1 월 1 일 자정에서 날짜 및 시간 값의 서식을 지정 하려면 범위 벗어난 경우 예외를 throw utc (협정 세계시)입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>  CTime::FormatGmt  
 에 해당 하는 형식이 지정 된 문자열을 생성 `CTime` 개체입니다.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>매개 변수  
 `pszFormat`  
 비슷한 서식 문자열로 지정 된 `printf` 문자열의 서식을 지정 합니다. 런타임 함수를 참조 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 대 한 자세한 내용은 합니다.  
  
 `nFormatID`  
 이 형식을 식별 하는 문자열의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 서식이 지정 된 시간을 포함 하는 합니다.  
  
### <a name="remarks"></a>설명  
 시간 값은 변환 되지 하 고 따라서 UTC를 반영 합니다.  
  
 이 메서드는 3000 년 12 월 31 일을 통해 1970 년 1 월 1 일 자정에서 날짜 및 시간 값의 서식을 지정 하려면 범위 벗어난 경우 예외를 throw utc (협정 세계시)입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CTime::Format](#format)합니다.  
  
##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP  
 에 저장 된 시간 정보를 변환 하려면이 멤버 함수 호출의 `CTime` Win32 호환 DBTIMESTAMP 구조에는 개체입니다.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dbts`  
 현재 현지 시간을 포함 하는 DBTIMESTAMP 구조체에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 결과 시간을 참조된 `dbts` 구조에 저장합니다. **DBTIMESTAMP** 이 함수에 의해 초기화 되는 데이터 구조를 갖습니다. 해당 **분수** 멤버가 0으로 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime  
 에 저장 된 시간 정보를 변환 하려면이 멤버 함수 호출의 `CTime` Win32 호환 되는 개체 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 구조입니다.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *timeDest*  
 에 대 한 참조는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 의 변환 된 날짜/시간 값을 보유 하는 구조는 `CTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 그렇지 않으면 false입니다.  
  
### <a name="remarks"></a>설명  
 `GetAsSystemTime` 결과 시간에 참조 된 저장 *timeDest* 구조입니다. `SYSTEMTIME` 이 함수에 의해 초기화 되는 데이터 구조를 갖습니다. 해당 **wMilliseconds** 멤버가 0으로 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime  
 반환 된 `CTime` 현재 시간을 나타내는 개체입니다.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>설명  
 현재 시스템 날짜 및 시간을 utc (협정 세계시)로 반환합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>  CTime::GetDay  
 의해 일 표시를 반환 합니다.는 `CTime` 개체입니다.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 범위 1-31에에서 현지 시간에 따라 해당 월의 일을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`, 내부, 정적으로 할당 된 버퍼를 사용 하 여 합니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek  
 나타내는 주의 일을 반환 된 `CTime` 개체입니다.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 현지 시간 기준 요일을 반환 합니다. 1 = 일요일, 2 = 월요일, 7 = 토요일.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>  CTime::GetGmtTm  
 가져옵니다는 **구조체 tm** 이에 포함 된 시간의 분해를 포함 하는 `CTime` 개체입니다.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>매개 변수  
 `ptm`  
 시간 데이터를 받을 버퍼를 가리킵니다. 이 포인터 이면 **NULL**, 예외가 throw 됩니다.  
  
### <a name="return-value"></a>반환 값  
 채워진 기능에 대 한 포인터 **구조체 tm** 시간 포함 파일에 정의 된 대로 합니다. 8. 참조 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 구조 레이아웃에 대 한 합니다.  
  
### <a name="remarks"></a>설명  
 `GetGmtTm` UTC를 반환합니다.  
  
 `ptm`가 `NULL`이 될 수 없는 경우 이전 동작으로 되돌리려면 원하는 `ptm` 수 `NULL` 내부, 정적으로 할당 된 버퍼를 사용 해야 함을 나타내려면 해제 `_SECURE_ATL`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>  CTime::GetHour  
 가 나타내는 시간을 반환 합니다는 `CTime` 개체입니다.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 0부터 23까지 범위에서 현지 시간을 기반으로 시간을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>  CTime::GetLocalTm  
 가져옵니다는 **구조체 tm** 이에 포함 된 시간의 분해 포함 된 `CTime` 개체입니다.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>매개 변수  
 `ptm`  
 시간 데이터를 받을 버퍼를 가리킵니다. 이 포인터 이면 **NULL**, 예외가 throw 됩니다.  
  
### <a name="return-value"></a>반환 값  
 채워진 기능에 대 한 포인터 **구조체 tm** 시간 포함 파일에 정의 된 대로 합니다. 8. 참조 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) 구조 레이아웃에 대 한 합니다.  
  
### <a name="remarks"></a>설명  
 `GetLocalTm` 현지 시간을 반환합니다.  
  
 `ptm`가 `NULL`이 될 수 없는 경우 이전 동작으로 되돌리려면 원하는 `ptm` 수 `NULL` 내부, 정적으로 할당 된 버퍼를 사용 해야 함을 나타내려면 해제 `_SECURE_ATL`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>  CTime::GetMinute  
 가 나타내는 분 단위는 `CTime` 개체입니다.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 0부터 59 까지의 범위에 현지 시간 기준 분을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetHour](#gethour)합니다.  
  
##  <a name="getmonth"></a>  CTime::GetMonth  
 가 나타내는 월 반환는 `CTime` 개체입니다.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 월 단위 범위는 1부터 12까지 현지 시간 기준 (1 = 1 월).  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetDay](#getday)합니다.  
  
##  <a name="getsecond"></a>  CTime::GetSecond  
 가 나타내는 두 번째 반환 된 `CTime` 개체입니다.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 두 번째 반환 0부터 59 까지의 범위에 현지 시간을 기반으로 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetHour](#gethour)합니다.  
  
##  <a name="gettime"></a>  CTime::GetTime  
 반환은 **__time64_t** 에 대 한 값은 지정 된 `CTime` 개체입니다.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>반환 값  
 **GetTime** 는 현재 사이의 시간 (초) 수를 반환 `CTime` 개체 및 1970 년 1 월 1 일입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>  CTime::GetYear  
 가 나타내는 연도 반환 된 `CTime` 개체입니다.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>반환 값  
 범위 1 월에에서 현지 시간 기준 연도 반환 1,1970 2038 년 1 월 18 일 (포함)에 있습니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 `GetLocalTm`를 사용 하는 내부 정적으로 할당 된 버퍼입니다. 다른 호출 때문에이 버퍼의 데이터 덮어쓰기 `CTime` 멤버 함수입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetDay](#getday)합니다.  
  
##  <a name="operator_eq"></a>  CTime::operator =  
 대입 연산자입니다.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `time`  
 새로운 날짜/시간 값입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 `CTime` 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 오버 로드 된 할당 연산자 복사는 원본 시간이 `CTime` 개체입니다. 내부 시간 저장소에는 `CTime` 개체는 표준 시간대와 무관 합니다. 표준 시간대 변환 할당 하는 동안 필요 하지 않습니다.  
  
##  <a name="operator_add_-"></a>  CTime::operator +,-  
 이러한 연산자는 더하기 및 빼기 `CTimeSpan` 및 `CTime` 개체입니다.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>매개 변수  
 *TimeSpan*  
 `CTimeSpan` 개체를 추가 하거나 뺄 수 있습니다.  
  
 `time`  
 `CTime` 개체 수를 뺀 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CTime` 또는 `CTimeSpan` 작업의 결과 나타내는 개체입니다.  
  
### <a name="remarks"></a>설명  
 `CTime` 절대 시간을 표시 하는 개체 `CTimeSpan` 개체 상대 시간을 나타냅니다. 처음 두 연산자는 더하기 및 빼기 수 있도록 `CTimeSpan` 개체에서 `CTime` 개체입니다. 세 번째 연산자를 사용 하면 1을 뺍니다 `CTime` 을 생성 하는 다른 개체는 `CTimeSpan` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTime::operator + =, =  
 이러한 연산자는 더하기 및 빼기는 `CTimeSpan` 개체와이 `CTime` 개체입니다.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CTimeSpan` 개체를 추가 하거나 뺄 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 `CTime` 개체입니다.  
  
### <a name="remarks"></a>설명  
 이러한 연산자를 사용 하면 추가 하 고 빼는 `CTimeSpan` 개체와이 `CTime` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>  CTime::Serialize64  
  
> [!NOTE]
>  이 메서드는 MFC 프로젝트에서 사용할 수만 있습니다.  
  
 멤버 변수 또는 보관에서 연관 된 데이터를 serialize 합니다.  
  
```  
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 `ar`  
 `CArchive` 업데이트 하려는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 `CArchive` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)


