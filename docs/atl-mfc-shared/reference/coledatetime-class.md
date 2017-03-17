---
title: "COleDateTime 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 34
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
ms.openlocfilehash: ecb32876e55c9801b28fefa1a189508ffbc8b78c
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetime-class"></a>COleDateTime 클래스
캡슐화 된 `DATE` OLE 자동화에 사용 되는 데이터 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```
class COleDateTime
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|`COleDateTime` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|서식이 지정 된 문자열 표현을 생성 한 `COleDateTime` 개체입니다.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 개체는 **DBTIMESTAMP** 데이터 구조입니다.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 개체는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 데이터 구조입니다.|  
|[COleDateTime::GetAsUDATE](#getasudate)|에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 로 **UDATE** 데이터 구조입니다.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|만듭니다는 `COleDateTime` (정적 멤버 함수)는 현재 시간을 나타내는 개체입니다.|  
|[COleDateTime::GetDay](#getday)|이 일을 반환 `COleDateTime` 개체 (1-31)을 나타냅니다.|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|이 요일을 반환 `COleDateTime` 개체가 나타내는 (일요일 = 1).|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|이 한 해의 날짜 반환 `COleDateTime` 개체가 나타내는 (1 월 1 = 1).|  
|[COleDateTime::GetHour](#gethour)|이 시간을 반환 `COleDateTime` 개체가 나타내는 (0-23).|  
|[COleDateTime::GetMinute](#getminute)|이 분을 반환 `COleDateTime` 개체가 나타내는 (0-59).|  
|[COleDateTime::GetMonth](#getmonth)|이 월을 반환 `COleDateTime` 개체 (1-12)를 나타냅니다.|  
|[COleDateTime::GetSecond](#getsecond)|이 두 번째 반환 `COleDateTime` 개체가 나타내는 (0-59).|  
|[COleDateTime::GetStatus](#getstatus)|이 작업의 상태 (유효성)를 가져옵니다 `COleDateTime` 개체입니다.|  
|[COleDateTime::GetYear](#getyear)|이 연도 반환 `COleDateTime` 개체가 나타내는 합니다.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|값을 설정 하 고 문자열에서 날짜/시간 값을 읽는 `COleDateTime`합니다.|  
|[COleDateTime::SetDate](#setdate)|이 값을 설정 `COleDateTime` 개체 지정된 된 날짜 전용 값입니다.|  
|[COleDateTime::SetDateTime](#setdatetime)|이 값을 설정 `COleDateTime` 개체를 지정 된 날짜/시간 값입니다.|  
|[COleDateTime::SetStatus](#setstatus)|이 작업의 상태 (유효성) 설정 `COleDateTime` 개체입니다.|  
|[COleDateTime::SetTime](#settime)|이 값을 설정 `COleDateTime` 개체 지정된 된 시간 전용 값입니다.|  
  
### <a name="public-operators"></a>Public 연산자  

|이름|설명|  
|----------|-----------------|  
|[COleDateTime::operator = =, COleDateTime::operator<,></,>](#coledatetime_relational_operators)|두 개를 비교 `COleDateTime` 값입니다.|  
|[COleDateTime::operator + COleDateTime::operator-](#operator_add_-)|더하기 및 빼기 `COleDateTime` 값입니다.|  
|[COleDateTime::operator + =,-= COleDateTime::operator](#operator_add_eq_-_eq)|더하기 및 빼기는 `COleDateTime` 값이 `COleDateTime` 개체입니다.|  
|[COleDateTime::operator =](#operator_eq)|복사본을 `COleDateTime` 값입니다.|  
|[날짜, COleDateTime::operator COleDateTime::operator 날짜 *](#operator_date)|변환 된 `COleDateTime` 값에 `DATE` 또는 `DATE*`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|기본 포함 **날짜** 이 `COleDateTime` 개체입니다.|  
|[COleDateTime::m_status](#m_status)|이 작업의 상태를 포함 `COleDateTime` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 `COleDateTime`기본 클래스는 없습니다.  
  
 항목에 대 한 가능한 형식 중 하나 이므로 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) OLE 자동화의 데이터 형식입니다. A `COleDateTime` 값 절대 날짜 및 시간 값을 나타냅니다.  
  
 `DATE` 형식이 부동 소수점 값으로 구현 됩니다. 일 자정에 1899 년 12 월 30 일에서 측정 됩니다. 다음 표에서 일부 날짜 및 관련된 값을 보여 줍니다.  
  
|날짜|값|  
|----------|-----------|  
|1899 년 12 월 29 일 자정|-1.0|  
|1899 년 12 월 29 일, 오전 6|-1.25|  
|1899 년 12 월 30 일 자정|0.0|  
|1899 년 12 월 31 일 자정|1.0|  
|1900 년 1 월 1 일 오전 6 시|2.25|  
  
> [!CAUTION]
>  위의 표에 되지만 자정 1899 년 12 월 30 일 이전 날짜 값이 음수가 되의 시간 값 하지 않는다는 note 합니다. 예를 들어 오전 6시 항상 일을 나타내는 정수 (1899 년 12 월 30 일) 후 양수 또는 음수 (하기 전에 1899 년 12 월 30 일) 인지에 관계 없이 0.25 소수 값으로 표시 됩니다. 즉, 간단한 부동 포인트 비교 정렬 잘못 됩니다는 `COleDateTime` 으로 1899 년 12 월 29 일 오전 6 시를 나타내는 **나중** 같은 날 오전 7 시를 나타내는 1 보다 합니다.  
  
 `COleDateTime` 클래스에서 9999 년 12 월 31 일 까지의 100, 년 1 월 1 일에서 날짜를 처리 합니다. `COleDateTime` 클래스 양력을 사용 하 여; 율리우스력 날짜를 지원 하지 않습니다. `COleDateTime`일광 절약 시간제를 무시합니다. (참조 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  사용할 수는 `%y` 1900에서 시작 하는 날짜에 대해서만 두 자리 연도 검색 하는 형식입니다. 사용 하는 경우는 `%y` 1900 년 이전의 날짜 코드에 형식 어설션 실패를 생성 합니다.  
  
 이 형식은 날짜 또는 시간 전용 값을 나타내는 사용 됩니다. 규칙에 따라 0 (1899 년 12 월 30 일) 날짜 시간 전용 값에 사용 되 고 시간이 00:00 (자정) 날짜 전용 값에 사용 됩니다.  
  
 만드는 경우는 `COleDateTime` 날짜를 사용 하 여 개체 보다 작거나 100이 고, 날짜는 수용 하지만 후속 호출을 `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, 및 `GetSecond` 실패 하 고-1을 반환 합니다. 이전에 두 자리 날짜를 사용할 수 있지만 날짜 100 또는 MFC 4.2에서 더 큰 이상 이어야 합니다.  
  
 문제를 피하려면 네 자리 날짜를 지정 합니다. 예:  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&1;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 에 대 한 기본 산술 연산을 `COleDateTime` 도우미 클래스를 사용 하는 값 [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)합니다. `COleDateTimeSpan`값에는 시간 간격을 정의합니다. 이러한 클래스 간의 관계는 사이 나오는 것과 유사한 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 및 [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)합니다.  
  
 에 대 한 자세한 내용은 `COleDateTime` 및 `COleDateTimeSpan` 클래스 문서를 참조 하십시오. [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>COleDateTime 관계형 연산자  
 비교 연산자입니다.  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `date`  
 **COleDateTime** 비교할 개체입니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  ATLASSERT 두 피연산자 중 하나가 유효 하지 않으면 발생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&13;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>예제  
 The operators **>=**, **\<=**, **>**, and **<**, will assert if the `COleDateTime` object is set to null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&170;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>COleDateTime::COleDateTime  
 `COleDateTime` 개체를 생성합니다.  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dateSrc`  
 기존 `COleDateTime` 새 복사할 개체 `COleDateTime` 개체입니다.  
  
 *varSrc*  
 기존 **VARIANT** 데이터 구조 (가능성이 있는 `COleVariant` 개체)를 날짜/시간 값을 변환할 수 ( `VT_DATE`) 새 복사 `COleDateTime` 개체입니다.  
  
 `dtSrc`  
 날짜/시간 ( **날짜**) 새 복사 될 값을 `COleDateTime` 개체입니다.  
  
 `timeSrc`  
 A `time_t` 또는 **__time64_t** 날짜/시간 값으로 변환 하 고 새 복사 될 값 `COleDateTime` 개체입니다.  
  
 *systimeSrc*  
 A `SYSTEMTIME` 날짜/시간 값으로 변환 하 고 새 복사 될 구조 `COleDateTime` 개체입니다.  
  
 `filetimeSrc`  
 A `FILETIME` 날짜/시간 값으로 변환 하 고 새 복사 될 구조 `COleDateTime` 개체입니다. `FILETIME` utc (협정 세계시)를 사용 하 여 구조에 현지 시간을 전달 하는 경우 결과 올바르지 않을 하므로입니다. 참조 [파일 시간을](http://msdn.microsoft.com/library/windows/desktop/ms724290) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 복사할 새 날짜 및 시간 값을 나타내는 `COleDateTime` 개체입니다.  
  
 `wDosDate`, `wDosTime`  
 날짜/시간 값으로 변환 하 고 새 복사 될 MS-DOS 날짜 및 시간 값 `COleDateTime` 개체입니다.  
  
 `dbts`  
 에 대 한 참조는 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) 현재 현지 시간을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 이러한 모든 생성자는 새로 만들기 `COleDateTime` 개체를 지정된 된 값으로 초기화 합니다. 다음 표에서 각 날짜 및 시간 구성 요소에 대 한 유효한 범위를 보여 줍니다.  
  
|날짜/시간 구성 요소|유효 범위|  
|--------------------------|-----------------|  
|연도|100 – 9999|  
|월|0 – 12|  
|일|0 – 31|  
|시간|0 – 23|  
|분|0 – 59|  
|두 번째|0 – 59|  
  
 일 구성 요소에 대 한 실제 상한 값에 따라 해당 월 및 연도 구성 요소 기반으로 합니다. 자세한 내용은 참조는 **SetDate** 또는 `SetDateTime` 멤버 함수입니다.  
  
 다음은 각 생성자의 간략 한 설명.  
  
- `COleDateTime(`**)** 생성 한 `COleDateTime` 0 (자정, 30 1899 년 12 월)으로 초기화 하는 개체입니다.  
  
- `COleDateTime(``dateSrc` **)** 생성 한 `COleDateTime` 기존 개체 `COleDateTime` 개체입니다.  
  
- `COleDateTime(`*varSrc* **)** 생성 한 `COleDateTime` 개체입니다. 변환 하려고 시도 `VARIANT` 구조 또는 [COleVariant](../../mfc/reference/colevariant-class.md) 날짜/시간 개체 ( `VT_DATE`) 값입니다. 변환 된 값에 새 복사 됩니다이 변환에 성공할 경우 `COleDateTime` 개체입니다. 없는 경우의 값은 `COleDateTime` 개체가 0 (자정, 30 1899 년 12 월)에 잘못 된 상태를 설정 합니다.  
  
- `COleDateTime(``dtSrc` **)** 생성 한 `COleDateTime` 에서 개체는 **날짜** 값입니다.  
  
- `COleDateTime(``timeSrc` **)** 생성 한 `COleDateTime` 에서 개체는 `time_t` 값입니다.  
  
- `COleDateTime(`*systimeSrc* **)** 생성 한 `COleDateTime` 에서 개체는 `SYSTEMTIME` 값입니다.  
  
- `COleDateTime(``filetimeSrc` **)** 생성 한 `COleDateTime` 에서 개체는 `FILETIME` 값입니다. 입니다. `FILETIME` utc (협정 세계시)를 사용 하 여 구조에 현지 시간을 전달 하는 경우 결과 올바르지 않을 하므로입니다. 참조 [파일 시간을](http://msdn.microsoft.com/library/windows/desktop/ms724290) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
- `COleDateTime(``nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** 생성 한 `COleDateTime` 개체는 지정 된 숫자 값에서입니다.  
  
- `COleDateTime(``wDosDate`, `wDosTime` **)** 생성 한 `COleDateTime` 개체는 지정 된 MS-DOS 날짜 및 시간 값에서입니다.  
  
 대 한 자세한 내용은 `time_t` 참조 데이터 형식에서 [시간](../../c-runtime-library/reference/time-time32-time64.md) 함수는 *런타임 라이브러리 참조*합니다.  
  
 자세한 내용은 참조는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 및 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
> [!NOTE]
>  사용 하 여 생성자 **DBTIMESTAMP** OLEDB.h 포함 되는 경우에 매개 변수는 사용할 수만 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&2;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>COleDateTime::Format  
 날짜/시간 값의 서식이 지정 된 표현을 만듭니다.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 로캘 플래그 중 하나를 나타냅니다.  
  
- `LOCALE_NOUSEROVERRIDE`사용자 지정 사용자 설정 대신 시스템 기본 로캘 설정을 사용 합니다.  
  
- `VAR_TIMEVALUEONLY`구문 분석 하는 동안 날짜 부분을 무시 합니다.  
  
- `VAR_DATEVALUEONLY`구문 분석 하는 동안 시간 부분을 무시 합니다.  
  
 `lcid`  
 변환 하는 데 사용할 로캘 ID를 나타냅니다. 언어 식별자에 대 한 자세한 내용은 참조 [언어 식별자](http://msdn.microsoft.com/library/windows/desktop/dd318691)합니다.  
  
 `lpszFormat`  
 유사한 문자열 서식는 `printf` 문자열의 형식을 지정 합니다. 각 서식 코드를 앞에 백분율 ( `%`) 서명, 해당 교체 `COleDateTime` 구성 요소입니다. 서식 문자열에 다른 문자는 반환 된 문자열에 변경 되지 않은 상태로 복사 됩니다. 런타임 함수를 참조 [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 에 대 한 자세한 내용은 합니다. 값과에 대 한 서식 지정 코드의 의미 `Format` 됩니다.  
  
- `%H`현재 날짜에 시간  
  
- `%M`현재 시간에서 분  
  
- `%S`현재 분의 초  
  
- `%%`백분율 기호  
  
 `nFormatID`  
 리소스 ID 형식 컨트롤 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 서식이 지정 된 날짜/시간 값이 포함 된 합니다.  
  
### <a name="remarks"></a>주의  
 하는 경우이 작업의 상태 `COleDateTime` 개체가 null 이면 반환 값은 빈 문자열입니다. 상태가 잘못 된 문자열 리소스 반환 문자열 지정 됩니다 `ATL_IDS_DATETIME_INVALID`합니다.  
  
 이 함수는 세 가지 형식에 대 한 간단한 설명은 다음과 같습니다.  
  
 `Format`( `dwFlags`, `lcid`)  
 이 양식을 언어 사양 (로캘 Id)를 사용 하 여 날짜 및 시간에 대 한 값의 형식을 합니다. 기본 매개 변수를 사용 하 여이 양식이 인쇄 날짜와 시간을 경우가 아니면 시간 부분은 0 (자정),이 경우 날짜만, 인쇄 날짜 부분은 0 (30 1899 년 12 월)에 있는 경우에 인쇄 됩니다. 날짜/시간 값은 0 (30 1899 년 12 월 자정), 자정 기본 매개 변수가 있는이 폼이 인쇄 됩니다.  
  
 `Format`( `lpszFormat`)  
 이 폼에서와 같이 앞에 백분율 기호 (%) 하는 특별 한 서식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 형식을 `printf`합니다. 서식 문자열은 함수에 매개 변수로 전달 됩니다. 서식 지정 코드에 대 한 자세한 내용은 참조 [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 런타임 라이브러리 참조에 있습니다.  
  
 `Format`( `nFormatID`)  
 이 폼에서와 같이 앞에 백분율 기호 (%) 하는 특별 한 서식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 형식을 `printf`합니다. 형식 문자열에는 리소스입니다. 이 문자열 리소스의 ID 매개 변수로 전달 됩니다. 서식 지정 코드에 대 한 자세한 내용은 참조 [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) 에 *런타임 라이브러리 참조*합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&3;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 개체는 **DBTIMESTAMP** 데이터 구조입니다.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dbts`  
 에 대 한 참조는 [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 결과 시간을 참조된 `dbts` 구조에 저장합니다. **DBTIMESTAMP** 이 함수에 의해 초기화 되는 데이터 구조에 포함 됩니다 해당 **분수** 멤버는&0;으로 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&4;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 개체는 `SYSTEMTIME` 데이터 구조입니다.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *sysTime*  
 에 대 한 참조는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 에서 변환 된 날짜/시간 값을 받을 구조는 `COleDateTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 성공 하면 **false** 아니면 변환에 실패 하는지는 `COleDateTime` 개체는 **NULL** 되었거나 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 `GetAsSystemTime`결과 시간에 참조 된 저장 *sysTime* 개체입니다. `SYSTEMTIME` 이 함수에 의해 초기화 되는 데이터 구조에 포함 됩니다 해당 **wMilliseconds** 멤버는&0;으로 설정 합니다.  
  
 참조 [GetStatus](#getstatus) 에 상태 정보에 대 한 자세한 내용은 보관에 대 한는 `COleDateTime` 개체입니다.  
  
##  <a name="getasudate"></a>COleDateTime::GetAsUDATE  
 에 시간을 얻기 위해이 메서드를 호출 하는 `COleDateTime` 개체는 **UDATE** 데이터 구조입니다.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `udate`  
 에 대 한 참조는 **UDATE** 에서 변환 된 날짜/시간 값을 받을 구조는 `COleDateTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 성공 하면 **false** 아니면 변환에 실패 하는지는 `COleDateTime` 개체는 **NULL** 되었거나 잘못 되었습니다.  
  
### <a name="remarks"></a>주의  
 A **UDATE** 구조 "압축 푼된"는 날짜를 나타냅니다.  
  
##  <a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 현재 날짜/시간 값을 반환 하도록이 정적 멤버 함수를 호출 합니다.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&5;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>COleDateTime::GetDay  
 이 날짜/시간 값으로 표현 되는 월의 일 수를 가져옵니다.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값을 나타내는 월의 일 `COleDateTime` 개체 또는 `COleDateTime::error` 일을 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 1에서 31 사이입니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&6;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 이 날짜/시간 값으로 표현 되는 월의 일 수를 가져옵니다.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값으로 표시 되는 요일을 `COleDateTime` 개체 또는 `COleDateTime::error` 요일을 차례로 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 1에서 7 사이의 여기서 1 = 일요일, 2 = 월요일, 하 고 있습니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&7;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 이 날짜/시간 값으로 표시 되는 연도의 일 수를 가져옵니다.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값으로 표시 되는 연도의 일 `COleDateTime` 개체 또는 `COleDateTime::error` 연간 일자를 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 1에서 366 사이의 여기서 1 월 1 일 = 1입니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&8;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>COleDateTime::GetHour  
 이 날짜/시간 값으로 표시 되는 시간을 가져옵니다.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값이 나타내는 시간 `COleDateTime` 개체 또는 `COleDateTime::error` 시간을 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 0에서 23 사이입니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&9;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>COleDateTime::GetMinute  
 이 날짜/시간 값으로 표시 되는 분을 가져옵니다.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값으로 표시 되는 분 `COleDateTime` 개체 또는 `COleDateTime::error` 분을 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 0에서 59 사이의 합니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 예를 참조 [GetHour](#gethour)합니다.  
  
##  <a name="getmonth"></a>COleDateTime::GetMonth  
 이 날짜/시간 값으로 표현 되는 월을 가져옵니다.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값을 나타내는 월 `COleDateTime` 개체 또는 `COleDateTime::error` 월을 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 1에서 12 사이입니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 예를 참조 [GetDay](#getday)합니다.  
  
##  <a name="getsecond"></a>COleDateTime::GetSecond  
 이 날짜/시간 값으로 표시 되 고 두 번째를 가져옵니다.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값으로 표시 되 고 두 번째 `COleDateTime` 개체 또는 `COleDateTime::error` 두 번째를 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 0에서 59 사이의 합니다.  
  
> [!NOTE]
>  `COleDateTime` 클래스 윤 초를 지원 하지 않습니다.  
  
 에 대 한 구현에 대 한 자세한 내용은 `COleDateTime`, 문서를 참조 하십시오 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>예제  
 예를 참조 [GetHour](#gethour)합니다.  
  
##  <a name="getstatus"></a>COleDateTime::GetStatus  
 상태 (유효성)를 가져옵니다는 주어진 `COleDateTime` 개체입니다.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 작업의 상태를 반환 `COleDateTime` 값입니다. 호출 하는 경우 **GetStatus** 에 `COleDateTime` 개체는 기본적으로 생성을 반환 합니다 유효 합니다. 호출 하는 경우 **GetStatus** 에 `COleDateTime` 생성자 집합을 null로 초기화 된 개체 **GetStatus** null을 반환 합니다. 참조 **주의** 에 대 한 자세한 내용은 합니다.  
  
### <a name="remarks"></a>주의  
 반환 값에 의해 정의 되는 **DateTimeStatus** 열거 형식 내에 정의 된는 `COleDateTime` 클래스입니다.  
  
 `enum DateTimeStatus`  
  
 `{`  
  
 `error = -1,`  
  
 `valid = 0,`  
  
 `invalid = 1,    // Invalid date (out of range, etc.)`  
  
 `null = 2,       // Literally has no value`  
  
 `};`  
  
 에 대 한 간략 한 설명은이 상태 값을 다음 목록을 참조 합니다.  
  
- `COleDateTime::error`날짜/시간 값의 일부를 가져오는 동안 오류가 발생 했음을 나타냅니다.  
  
- **COleDateTime::valid** 나타냅니다가 `COleDateTime` 개체는 유효 합니다.  
  
- **COleDateTime::invalid** 나타냅니다가 `COleDateTime` 개체가 유효 하지 않습니다; 즉, 해당 값 올바르지 않을 수 있습니다.  
  
- **COleDateTime::null** 나타냅니다가 `COleDateTime` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 c + +가 아니라 "값이 없는 것"의 데이터베이스 의미에서 "null" **NULL**.)  
  
 상태는 `COleDateTime` 개체가 다음과 같은 경우에 유효 하지 않습니다.  
  
-   해당 값에서 설정 된 경우는 **VARIANT** 또는 `COleVariant` 날짜/시간 값으로 변환 될 수 있는 값입니다.  
  
-   해당 값에서 설정 된 경우는 `time_t`, `SYSTEMTIME`, 또는 `FILETIME` 유효한 날짜/시간 값으로 변환 될 수 있는 값입니다.  
  
-   해당 값 설정 되어 있으면 `SetDateTime` 잘못 된 매개 변수 값이 있습니다.  
  
-   발생 한 경우이 개체는 오버플로 또는 언더플로 산술 할당 작업 중 즉, `+=` 또는 `-=`합니다.  
  
-   잘못 된 값이이 개체에 할당 된.  
  
-   이 개체의 상태를 사용 하 여 올바르지 않은 명시적으로 설정 된 경우 `SetStatus`합니다.  
  
 작업에 대 한 자세한 내용은 하는 다음 멤버 함수를 참조 하십시오 잘못 된 상태를 설정할 수 있습니다.  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [연산자 +,-](#operator_add_-)  
  
- [-= 연산자 + =](#operator_add_eq_-_eq)  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&10;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>COleDateTime::GetYear  
 이 날짜/시간 값으로 표시 되는 연도를 가져옵니다.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 값에 의해 표시 되는 연도의 `COleDateTime` 개체 또는 `COleDateTime::error` 연도 얻을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 유효한 반환 값의 범위는 세기를 포함 하는 100에서 9999 사이.  
  
 이 값을 쿼리 하는 다른 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetDay](#getday)합니다.  
  
##  <a name="m_dt"></a>COleDateTime::m_dt  
 내부 **날짜** 이 대 한 구조 `COleDateTime` 개체입니다.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>주의  
  
> [!CAUTION]
>  값을 변경의 **날짜** 이 함수에 의해 반환 된 포인터에 액세스 한 개체가이 값을 변경 `COleDateTime` 개체입니다. 이 상태는 변경 되지 않습니다 `COleDateTime` 개체입니다.  
  
 구현에 대 한 자세한 내용은 **날짜** 개체, 문서를 참조 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="m_status"></a>COleDateTime::m_status  
 이 작업의 상태를 포함 `COleDateTime` 개체입니다.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>주의  
 이 데이터 멤버의 형식은 열거 형식 **DateTimeStatus**, 내에서 정의 되는 `COleDateTime` 클래스입니다. 참조 [COleDateTime::GetStatus](#getstatus) 대 한 자세한 내용은 합니다.  
  
> [!CAUTION]
>  이 데이터 멤버는 고급 프로그래밍 시나리오입니다. 인라인 멤버 함수를 사용 해야 [GetStatus](#getstatus) 및 [SetStatus](#setstatus)합니다. 참조 `SetStatus` 이 데이터 멤버를 명시적으로 설정 하는 것에 대 한 추가 주의 사항에 대 한 합니다.  
  
##  <a name="operator_eq"></a>COleDateTime::operator =  
 복사본을 `COleDateTime` 값입니다.  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>주의  
 이러한 오버 로드 된 대입 연산자 복사할 원본 날짜/시간 값이 `COleDateTime` 개체입니다. 이러한 각 한 간단한 설명을 할당 연산자 다음과 오버 로드 됩니다.  
  
- **operator = (** `dateSrc` **)** 값과 피연산자의 상태를 복사할이 `COleDateTime` 개체입니다.  
  
- **연산자 = (** *varSrc* **)** 경우 변환은 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 값 (또는 [COleVariant](../../mfc/reference/colevariant-class.md) 개체)를 날짜/시간 ( `VT_DATE`)은 성공적으로 변환 된 값이 복사 됩니다 `COleDateTime` 개체와 해당 상태에 유효한 설정 됩니다. 이 개체의 값 0 (30 1899 년 12 월 자정)로 설정 되는 변환이 성공한 경우에 유효 하지 않은 상태입니다.  
  
- **연산자 = (** `dtSrc` **)** 는 **날짜** 값은이에 복사 `COleDateTime` 개체와 해당 상태에 유효한 설정 됩니다.  
  
- **operator = (** `timeSrc` **)** 는 `time_t` 또는 **__time64_t** 값은 변환 하 고이에 복사 `COleDateTime` 개체입니다. 변환이 성공 하는 경우이 개체의 상태가 설정은 올바르지 않습니다. 실패할 경우 설정 되어 있는지를 잘못 되었습니다.  
  
- **operator = (** *systimeSrc* **)** 는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 값은 변환 하 고이에 복사 `COleDateTime` 개체입니다. 변환이 성공 하는 경우이 개체의 상태가 설정은 올바르지 않습니다. 실패할 경우 설정 되어 있는지를 잘못 되었습니다.  
  
- **operator = (** `udate` **)** 는 **UDATE** 값은 변환 하 고이에 복사 `COleDateTime` 개체입니다. 변환이 성공 하는 경우이 개체의 상태가 설정은 올바르지 않습니다. 실패할 경우 설정 되어 있는지를 잘못 되었습니다. A **UDATE** 구조 "압축 푼된"는 날짜를 나타냅니다. 함수를 참조 [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) 대 한 자세한 내용은 합니다.  
  
- **operator = (** `filetimeSrc` **)** 는 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 값은 변환 하 고이에 복사 `COleDateTime` 개체입니다. 변환이 성공 하는 경우이 개체의 상태가 설정은 올바르지 않습니다. 그렇지 않으면 설정에 잘못 되었습니다. `FILETIME`utc (협정 세계시)을 사용 하므로 UTC 시간 구조에 전달 하면 결과 현지 시간을 UTC 시간에서 변환 되 고 변형 시간으로 저장 됩니다. 이 동작은 Visual c + + 6.0 및 Visual c + +.NET 2003 s p 2에서와 같습니다. 참조 [파일 시간을](http://msdn.microsoft.com/library/windows/desktop/ms724290) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
 자세한 내용은 참조는 [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 대 한 자세한 내용은 `time_t` 참조 데이터 형식에서 [시간](../../c-runtime-library/reference/time-time32-time64.md) 함수는 *런타임 라이브러리 참조*합니다.  
  
 자세한 내용은 참조는 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) 및 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="operator_add_-"></a>COleDateTime::operator +,-  
 더하기 및 빼기 **ColeDateTime** 값입니다.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>주의  
 `COleDateTime`개체는 절대 시간을 나타냅니다. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) 개체 상대 시간을 나타냅니다. 처음 두 연산자를 사용 하면 더하기 및 빼기 수 있도록는 `COleDateTimeSpan` 에서 값을 `COleDateTime` 값입니다. 세 번째 연산자를 사용 하면 빼면 `COleDateTime` 값에서 생성 하는 다른 값을 `COleDateTimeSpan` 값입니다.  
  
 피연산자 중 하나가 null이 고, 결과의 상태 면 `COleDateTime` 값은 null입니다.  
  
 하는 경우 결과 `COleDateTime` 값 범위에 사용할 수 있는 값의 상태를 벗어 났 `COleDateTime` 값이 잘못 되었습니다.  
  
 피연산자 중 하나가 잘못 되었으며 다른가 null이 아닐 경우 결과의 상태 `COleDateTime` 값이 잘못 되었습니다.  
  
 ** + ** 및 ** - ** 경우 연산자는 어설션는 `COleDateTime` 개체가 설정 null로 합니다. 참조 [COleDateTime 관계형 연산자](#coledatetime_relational_operators) 대 한 예제입니다.  
  
 유효 하 고, 잘못 된 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&12;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTime::operator + =, =  
 더하기 및 빼기는 **ColeDateTime** 값이 `COleDateTime` 개체입니다.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>주의  
 이러한 연산자를 사용 하면 더하기 및 빼기 수 있도록는 `COleDateTimeSpan` 값이에서 `COleDateTime`합니다. 피연산자 중 하나가 null이 고, 결과의 상태 면 `COleDateTime` 값은 null입니다.  
  
 하는 경우 결과 `COleDateTime` 값 범위에 허용 되는 값을이 작업의 상태를 벗어 났 `COleDateTime` 값이 설정에 잘못 되었습니다.  
  
 피연산자 중 하나가 잘못 되었으며 다른가 null이 아닐 경우 결과의 상태 `COleDateTime` 값이 잘못 되었습니다.  
  
 유효 하 고, 잘못 된 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.  
  
 ** += ** 및 ** -= ** 경우 연산자는 어설션는 `COleDateTime` 개체가 설정 null로 합니다. 참조 [COleDateTime 관계형 연산자](#coledatetime_relational_operators) 대 한 예제입니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="operator_date"></a>COleDateTime::operator 날짜  
 변환 된 **ColeDateTime** 값에 **날짜**합니다.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>주의  
 이 연산자는 반환 된 **날짜** 개체 값이 복사 됩니다 `COleDateTime` 개체입니다. 구현에 대 한 자세한 내용은 **날짜** 개체, 문서를 참조 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
 **날짜** 경우 연산자는 어설션는 `COleDateTime` 개체가 설정 null로 합니다. 참조 [COleDateTime 관계형 연산자](#coledatetime_relational_operators) 대 한 예제입니다.  
  
##  <a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 날짜/시간 값을 읽을 수는 문자열을 구문 분석 합니다.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszDate`  
 구문 분석 하는 null로 끝나는 문자열에 대 한 포인터입니다. 자세한 내용은 설명을 참조하세요.  
  
 `dwFlags`  
 로캘 설정 하 고 구문 분석에 대 한 플래그를 나타냅니다. 하나 이상의 다음 플래그:  
  
- **LOCALE_NOUSEROVERRIDE** 사용자 지정 사용자 설정 대신 시스템 기본 로캘 설정을 사용 합니다.  
  
- **VAR_TIMEVALUEONLY** 구문 분석 하는 동안 날짜 부분을 무시 합니다.  
  
- **VAR_DATEVALUEONLY** 구문 분석 하는 동안 시간 부분을 무시 합니다.  
  
 `lcid`  
 변환 하는 데 사용할 로캘 ID를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 경우 문자열 성공적으로 변환 되었습니다 날짜/시간 값, 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 문자열이 날짜/시간으로 성공적으로 변환 된 경우 값을이 값 `COleDateTime` 개체 유효한 해당 값 및 해당 상태를로 설정 됩니다.  
  
> [!NOTE]
>  연도 값 까지입니다 100에서 9999 사이 있어야 합니다.  
  
 `lpszDate` 매개 변수는 다양 한 형식의 걸릴 수 있습니다. 예를 들어 다음 문자열에 허용 되는 날짜/시간 형식이 포함:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year,`  
  
 `// even in a 'short date' format`  
  
 로캘 ID 영향을 미칠 수도 문자열 형식 날짜/시간 값으로 변환에 사용할 수 있는지 여부를 메모 합니다.  
  
 경우 **VAR_DATEVALUEONLY**, 시간 값 0, 시간 또는 자정으로 설정 됩니다. 경우 **VAR_TIMEVALUEONLY**, 날짜 값 30 1899 년 12 월을 의미 하는 날짜 0으로 설정 됩니다.  
  
 이 작업의 상태 숫자 오버플로 발생 한 경우 또는 문자열을 날짜/시간 값으로 변환할 수 있는 경우 `COleDateTime` 개체가 유효 하지 않습니다.  
  
 범위 및 구현 하는 방법에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="setdate"></a>COleDateTime::SetDate  
 이 날짜 설정 `COleDateTime` 개체입니다.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nYear`, `nMonth`, `nDay`  
 날짜 구성 요소를이 복사할 `COleDateTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우에는 0 값이 `COleDateTime` 개체를 설정 했습니다 성공적이 고, 그러지 않으면 1입니다. 반환 값이 기반으로 **DateTimeStatus** 열거 형식입니다. 자세한 내용은 참조는 [SetStatus](#setstatus) 멤버 함수입니다.  
  
### <a name="remarks"></a>주의  
 날짜는 지정된 된 값으로 설정 됩니다. 시간 시간 0으로 자정으로 설정 됩니다.  
  
 범위 매개 변수 값에 대 한 다음 표를 참조 하십시오.  
  
|매개 변수|범위|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
  
 월의 날짜를 오버플로 하는 경우 다음 달과 달의 올바른 날짜 변환 됩니다 및/또는 연도 그에 따라 증가 합니다. 일 값을&0;으로 이전 달의 마지막 날을 나타냅니다. 동작은 동일 `SystemTimeToVariantTime`합니다.  
  
 이 개체의 상태가 설정은 매개 변수에 의해 지정 된 날짜 값 올바르지 않으면 **COleDateTime::invalid**합니다. 사용 해야 [GetStatus](#getstatus) 의 유효성을 검사 하는 **날짜** 값을 가정 하지 않아야 하는 값을 [m_dt](#m_dt) 수정 되지 않은 상태로 유지 됩니다.  
  
 날짜 값의 몇 가지 예는 다음과 같습니다.  
  
|`nYear`|`nMonth`|`nDay`|값|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29 2000 년 2 월|  
|1776|7|4|4 년 7 월 1776|  
|1925|4|35|35 년 4 월 1925 (잘못 된 날짜)|  
|10000|1|1|1 년 1 월 10000 (잘못 된 날짜)|  
  
 날짜와 시간을 설정 하려면 참조 [COleDateTime::SetDateTime](#setdatetime)합니다.  
  
 이 값을 쿼리 하는 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities #&11;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>COleDateTime::SetDateTime  
 이 작업의 시간과 날짜를 설정 `COleDateTime` 개체입니다.  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 이로 복사 되는 날짜 및 시간 구성 요소를 나타내는 `COleDateTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우에는 0 값이 `COleDateTime` 개체를 설정 했습니다 성공적이 고, 그러지 않으면 1입니다. 반환 값이 기반으로 **DateTimeStatus** 열거 형식입니다. 자세한 내용은 참조는 [SetStatus](#setstatus) 멤버 함수입니다.  
  
### <a name="remarks"></a>주의  
 범위 매개 변수 값에 대 한 다음 표를 참조 하십시오.  
  
|매개 변수|범위|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 월의 날짜를 오버플로 하는 경우 다음 달과 달의 올바른 날짜 변환 됩니다 및/또는 연도 그에 따라 증가 합니다. 일 값을&0;으로 이전 달의 마지막 날을 나타냅니다. 동작은 동일 [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450)합니다.  
  
 매개 변수에 의해 지정 된 날짜 또는 시간 값이이 개체의 상태가 유효 하지 않으며이 개체의 값으로 설정 됩니다 잘못 되었으면 변경 되지 않습니다.  
  
 시간 값의 몇 가지 예는 다음과 같습니다.  
  
|`nHour`|`nMin`|`nSec`|값|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|유효하지 않음|  
|9|60|0|유효하지 않음|  
  
 날짜 값의 몇 가지 예는 다음과 같습니다.  
  
|`nYear`|`nMonth`|`nDay`|값|  
|-------------|--------------|------------|-----------|  
|1995|4|15|15 년 4 월 1995 년|  
|1789|7|14|17 년 7 월 1789|  
|1925|2|30|유효하지 않음|  
|10000|1|1|유효하지 않음|  
  
 참조만으로 날짜를 설정 하려면 [COleDateTime::SetDate](#setdate)합니다. 참조만 시간을 설정 하려면 [COleDateTime::SetTime](#settime)합니다.  
  
 이 값을 쿼리 하는 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetStatus](#getstatus)합니다.  
  
##  <a name="setstatus"></a>COleDateTime::SetStatus  
 이 작업의 상태를 설정 `COleDateTime` 개체입니다.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *status*  
 새 상태 값이 `COleDateTime` 개체입니다.  
  
### <a name="remarks"></a>주의  
 *상태* 으로 매개 변수 값이 정의 **DateTimeStatus** 열거 형식 내에 정의 된는 `COleDateTime` 클래스입니다. 참조 [COleDateTime::GetStatus](#getstatus) 대 한 자세한 내용은 합니다.  
  
> [!CAUTION]
>  이 함수는 고급 프로그래밍 시나리오에 사용 합니다. 이 함수는이 개체의에서 데이터를 변경 하지 않습니다. 상태를 설정 하 여 가장 자주 사용 됩니다 `null` 또는 **잘못 된**합니다. 할당 연산자 ( [연산자 =](#eq)) 및 [SetDateTime](#setdatetime) 수행 원본 값에 따라 개체의 상태를 설정 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [GetStatus](#getstatus)합니다.  
  
##  <a name="settime"></a>COleDateTime::SetTime  
 이 작업의 시간을 설정 `COleDateTime` 개체입니다.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nHour`, `nMin`, `nSec`  
 시간 구성 요소를이 복사할 `COleDateTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 경우에는 0 값이 `COleDateTime` 개체를 설정 했습니다 성공적이 고, 그러지 않으면 1입니다. 반환 값이 기반으로 **DateTimeStatus** 열거 형식입니다. 자세한 내용은 참조는 [SetStatus](#setstatus) 멤버 함수입니다.  
  
### <a name="remarks"></a>주의  
 시간이 지정된 된 값으로 설정 됩니다. 날짜 날짜 0, 즉 30 1899 년 12 월에 설정 됩니다.  
  
 범위 매개 변수 값에 대 한 다음 표를 참조 하십시오.  
  
|매개 변수|범위|  
|---------------|------------|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 매개 변수에 의해 지정 된 값에 올바르지 않은 시간이이 개체의 상태가 유효 하지 않으며이 개체의 값에 설정 된 경우 변경 되지 않습니다.  
  
 시간 값의 몇 가지 예는 다음과 같습니다.  
  
|`nHour`|`nMin`|`nSec`|값|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|유효하지 않음|  
|9|60|0|유효하지 않음|  
  
 날짜와 시간을 설정 하려면 참조 [COleDateTime::SetDateTime](#setdatetime)합니다.  
  
 이 값을 쿼리 하는 멤버 함수에 대 한 내용은 `COleDateTime` 개체 멤버 함수는 다음을 참조 하십시오.  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTime` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [SetDate](#setdate)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleVariant 클래스](../../mfc/reference/colevariant-class.md)   
 [CTime 클래스](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)




