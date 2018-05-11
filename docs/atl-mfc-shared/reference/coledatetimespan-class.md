---
title: COleDateTimeSpan 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1941984093879ba22921d19580618ce8caa04b38
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan 클래스
상대 시간을, 시간 범위를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|`COleDateTimeSpan` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|형식이 지정 된 문자열 표현을 생성 한 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::GetDays](#getdays)|두 일 부분을 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetHours](#gethours)|이 범위의 시간 부분을 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|이 분 부분을 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|이 범위의 두 번째 부분을 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|이 상태 (유효성)를 가져옵니다. `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|이 일 수가 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|이 시간 수를 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|이 시간 (분)의 수를 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|이 시간 (초)의 수를 반환 `COleDateTimeSpan` 개체가 나타내는입니다.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|이 값을 설정 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|이 상태 (유효성) 설정 `COleDateTimeSpan` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|||  
|-|-|  
|[연산자 +,-](#operator_add_-)|추가, subtract, 및에 대 한 기호를 변경할 `COleDateTimeSpan` 값입니다.|  
|[operator + =, =](#operator_add_eq_-_eq)|더하기 및 빼기는 `COleDateTimeSpan` 값이 `COleDateTimeSpan` 값입니다.|  
|[operator =](#operator_eq)|복사는 `COleDateTimeSpan` 값입니다.|  
|[연산자 = =, <, < =](#coledatetimespan_relational_operators)|두 개를 비교 `COleDateTimeSpan` 값입니다.|  
|[연산자 double](#operator_double)|이 변환 `COleDateTimeSpan` 값을 한 **double**합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|기본 포함 **double** 이 `COleDateTimeSpan` 개체입니다.|  
|[COleDateTimeSpan::m_status](#m_status)|이 항목의 상태를 포함 `COleDateTimeSpan` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `COleDateTimeSpan` 기본 클래스는 없습니다.  
  
 A `COleDateTimeSpan` 시간 일 동안에서 유지 합니다.  
  
 `COleDateTimeSpan` 해당 도우미 클래스와 함께 사용 [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)합니다. `COleDateTime` 캡슐화 된 **날짜** OLE 자동화의 데이터 형식입니다. `COleDateTime` 절대 시간 값을 나타냅니다. 모든 `COleDateTime` 계산 관련 `COleDateTimeSpan` 값입니다. 이러한 클래스 간의 관계는 간의 비슷합니다 [CTime](../../atl-mfc-shared/reference/ctime-class.md) 및 [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)합니다.  
  
 대 한 자세한 내용은 `COleDateTime` 및 `COleDateTimeSpan` 클래스, 문서를 참조 하십시오. [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>  COleDateTimeSpan 관계형 연산자  
 비교 연산자입니다.  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *dateSpan*  
 비교할 `COleDateTimeSpan`입니다.  
  
### <a name="return-value"></a>반환 값  
 이러한 연산자는 두 개의 날짜/시간 범위 값을 비교 하 고 반환 **true** 조건이 true이 고, 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  ATLASSERT 피연산자 중 하나가 유효 하지 않을 경우 발생 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>  COleDateTimeSpan::COleDateTimeSpan  
 `COleDateTimeSpan` 개체를 생성합니다.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dblSpanSrc`  
 복사할 새 일 수가 `COleDateTimeSpan` 개체입니다.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 복사할 새 날짜 및 시간 값을 나타내는 `COleDateTimeSpan` 개체입니다.  
  
### <a name="remarks"></a>설명  
 새로 만들기 이러한 생성자의 모든 `COleDateTimeSpan` 개체를 지정된 된 값으로 초기화 합니다. 이 생성자의 각 간략 한 설명은 다음과 같습니다.  
  
- **COleDateTimeSpan ()** 생성 한 `COleDateTimeSpan` 0으로 초기화 하는 개체입니다.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** 생성 한 `COleDateTimeSpan` 에서 부동 소수점 값 개체입니다.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)**  생성 된 `COleDateTimeSpan` 개체가 지정된 된 숫자 값으로 초기화 합니다.  
  
 새 상태 `COleDateTimeSpan` 개체가 유효한로 설정 합니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>  COleDateTimeSpan::Format  
 형식이 지정 된 문자열 표현을 생성 한 `COleDateTimeSpan` 개체입니다.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `pFormat`  
 유사한 문자열 서식는 `printf` 문자열의 서식을 지정 합니다. 형식 지정 코드를 앞에 백분율 ( `%`) 로그인을 하면 해당 대체 `COleDateTimeSpan` 구성 요소입니다. 서식 문자열에 다른 문자는 반환 된 문자열에 변경 되지 않고 복사 됩니다. 값 및에 대 한 형식 지정 코드의 의미 **형식** 아래와 같습니다.  
  
- **%H** 현재 날짜에 시간  
  
- **%M** 현재 시간에서 분  
  
- **%S** 현재 분의 시간 (초)  
  
- **%%** 백분율 기호  
  
 위에 나열 된 4 개의 형식 코드는 형식을 허용 하는 유일한 코드입니다.  
  
-  
  
 `nID`  
 형식 컨트롤 문자열에 대 한 리소스 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 서식이 지정 된 날짜/시간 범위 값이 들어 있는입니다.  
  
### <a name="remarks"></a>설명  
 시간 범위 값의 서식이 지정 된 표현 하기 위해 이러한 함수를 호출 합니다. 경우이 상태의 `COleDateTimeSpan` 개체 null 이면 반환 값은 빈 문자열입니다. 반환 문자열은 문자열 리소스에서 지정 된 상태가 유효 하지 않을 경우 **IDS_INVALID_DATETIMESPAN**합니다.  
  
 이 함수에 대 한 폼에 대 한 간단한 설명은 다음과 같습니다.  
  
 **형식 (** `pFormat` **)**  
 이 폼에서와 같이 앞에 백분율 기호 (%) 하는 특별 한 형식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 서식을 `printf`합니다. 서식 문자열은 함수에 매개 변수로 전달 됩니다.  
  
 **형식 (** `nID` **)**  
 이 폼에서와 같이 앞에 백분율 기호 (%) 하는 특별 한 형식 지정 코드를 포함 하는 형식 문자열을 사용 하 여 값의 서식을 `printf`합니다. 형식 문자열 리소스입니다. 이 문자열 리소스의 ID는 매개 변수로 전달 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>  COleDateTimeSpan::GetDays  
 이 날짜/시간 범위 값의 일 부분을 검색합니다.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 날짜/시간 범위 값의 일 부분을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 값 사이의이 함수 범위에서 약-3,615,000 및 3,615,000 합니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>  COleDateTimeSpan::GetHours  
 이 날짜/시간 범위 값의 시간 부분을 검색합니다.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 날짜/시간 범위 값의 시간 부분입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위-23에서 23 사이의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>  COleDateTimeSpan::GetMinutes  
 이 날짜/시간 범위 값의 분 부분을 검색합니다.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 날짜/시간 범위 값의 분 부분입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위-59에서 59 사이의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>  COleDateTimeSpan::GetSeconds  
 이 날짜/시간 범위 값의 두 번째 부분을 검색합니다.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 날짜/시간 범위 값의 초 부분입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위-59에서 59 사이의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>  COleDateTimeSpan::GetStatus  
 이 상태 (유효성)를 가져옵니다. `COleDateTimeSpan` 개체입니다.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 상태 `COleDateTimeSpan` 값입니다.  
  
### <a name="remarks"></a>설명  
 반환 값에 의해 정의 되는 **DateTimeSpanStatus** 열거 형식 내에 정의 된는 `COleDateTimeSpan` 클래스입니다.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```  
  
 에 대 한 간략 한 설명은이 상태 값을 다음 목록을 참조 합니다.  
  
- **COleDateTimeSpan::valid** 나타냅니다가 `COleDateTimeSpan` 개체는 유효 합니다.  
  
- **COleDateTimeSpan::invalid** 나타냅니다가 `COleDateTimeSpan` 개체가 잘못 되었습니다; 즉, 해당 값 올바르지 않을 수 있습니다.  
  
- **COleDateTimeSpan::null** 나타냅니다가 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 c + +와 달리 "값이 없는 것"의 데이터베이스 의미에서 "null" **NULL**.)  
  
 상태는 `COleDateTimeSpan` 개체가 다음과 같은 경우에 유효 하지 않습니다.  
  
-   발생 한 경우이 개체에 오버플로 또는 언더플로가 발생 하는 동안 산술 할당 연산 즉, `+=` 또는 `-=`합니다.  
  
-   이 개체에 잘못 된 값이 할당 되었으면 합니다.  
  
-   이 개체의 상태가 잘못 사용 하 여 명시적으로 설정 된 경우 `SetStatus`합니다.  
  
 에 잘못 된 상태를 설정할 수 있는 작업에 대 한 자세한 내용은 참조 [COleDateTimeSpan::operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 및 [COleDateTimeSpan::operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)합니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="gettotaldays"></a>  COleDateTimeSpan::GetTotalDays  
 일 단위로이 날짜/시간 범위 값을 검색 합니다.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 일 단위로이 날짜/시간 범위 값입니다. 이 함수는 double를 반환할 수 있도록 프로토타입화 경우에 항상 정수 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위 사이 약-3.65e6 3.65e6의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>  COleDateTimeSpan::GetTotalHours  
 시간 단위로이 날짜/시간 범위 값을 검색 합니다.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 시간 단위로이 날짜/시간 범위 값입니다. 이 함수는 double를 반환할 수 있도록 프로토타입화 경우에 항상 정수 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위 사이 약-8.77e7 8.77e7의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 예를 참조 [GetTotalDays](#gettotaldays)합니다.  
  
##  <a name="gettotalminutes"></a>  COleDateTimeSpan::GetTotalMinutes  
 분 단위로이 날짜/시간 범위 값을 검색 합니다.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 이 날짜/시간 범위 값은 분 단위로 표현 합니다. 이 함수는 double를 반환할 수 있도록 프로토타입화 경우에 항상 정수 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수 범위 사이 약-5.26e9 5.26e9의 반환 값입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 예를 참조 [GetTotalDays](#gettotaldays)합니다.  
  
##  <a name="gettotalseconds"></a>  COleDateTimeSpan::GetTotalSeconds  
 초이 날짜/시간 범위 값을 검색 합니다.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 초이 날짜/시간 범위 값입니다. 이 함수는 double를 반환할 수 있도록 프로토타입화 경우에 항상 정수 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 반환 값 약-3.16e11를 3.16e11 사이의 범위입니다.  
  
 값을 쿼리 하는 다른 함수에 대 한는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>예제  
 예를 참조 [GetTotalDays](#gettotaldays)합니다.  
  
##  <a name="m_span"></a>  COleDateTimeSpan::m_span  
 내부 **double** 값이 `COleDateTime` 개체입니다.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>설명  
 이 값은 날짜/시간 범위 (일) 표현합니다.  
  
> [!CAUTION]
>  에 값을 변경는 **double** 데이터 멤버는이 값을 변경 하면 `COleDateTimeSpan` 개체입니다. 이 상태를 변경 하지는 않습니다 `COleDateTimeSpan` 개체입니다.  
  
##  <a name="m_status"></a>  COleDateTimeSpan::m_status  
 이 데이터 멤버에 대 한 형식이 열거 형식이 **DateTimeSpanStatus**, 내에서 정의 되는 `COleDateTimeSpan` 클래스입니다.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>설명  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 에 대 한 간략 한 설명은이 상태 값을 다음 목록을 참조 합니다.  
  
- **COleDateTimeSpan::valid** 나타냅니다가 `COleDateTimeSpan` 개체는 유효 합니다.  
  
- **COleDateTimeSpan::invalid** 나타냅니다가 `COleDateTimeSpan` 개체가 잘못 되었습니다; 즉, 해당 값 올바르지 않을 수 있습니다.  
  
- **COleDateTimeSpan::null** 나타냅니다가 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 c + +와 달리 "값이 없는 것"의 데이터베이스 의미에서 "null" **NULL**.)  
  
 상태는 `COleDateTimeSpan` 개체가 다음과 같은 경우에 유효 하지 않습니다.  
  
-   발생 한 경우이 개체에 오버플로 또는 언더플로가 발생 하는 동안 산술 할당 연산 즉, `+=` 또는 `-=`합니다.  
  
-   이 개체에 잘못 된 값이 할당 되었으면 합니다.  
  
-   이 개체의 상태가 잘못 사용 하 여 명시적으로 설정 된 경우 [SetStatus](#setstatus)합니다.  
  
 에 잘못 된 상태를 설정할 수 있는 작업에 대 한 자세한 내용은 참조 [COleDateTimeSpan::operator +,-](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) 및 [COleDateTimeSpan::operator + =,-=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq)합니다.  
  
> [!CAUTION]
>  이 데이터 멤버는 고급 프로그래밍 시나리오에 대 한 합니다. 인라인 멤버 함수를 사용 해야 [GetStatus](#getstatus) 및 [SetStatus](#setstatus)합니다. 참조 `SetStatus` 이 데이터 멤버를 명시적으로 설정 하는 것에 대 한 추가 주의 사항에 대 한 합니다.  
  
 에 대 한 범위에 대 한 자세한 내용은 `COleDateTimeSpan` 문서를 참조 하는 값을 [날짜 및 시간: 자동화 지원을](../../atl-mfc-shared/date-and-time-automation-support.md)합니다.  
  
##  <a name="operator_eq"></a>  COleDateTimeSpan::operator =  
 복사는 `COleDateTimeSpan` 값입니다.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>설명  
 이 오버 로드 된 할당 연산자 소스 날짜/시간 범위 값이이에 복사 `COleDateTimeSpan` 개체입니다.  
  
##  <a name="operator_add_-"></a>  COleDateTimeSpan::operator +,-  
 추가, subtract, 및에 대 한 기호를 변경할 `COleDateTimeSpan` 값입니다.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>설명  
 처음 두 연산자를 사용 하 여 추가 하 고 날짜/시간 범위 값을 뺄 수 있도록 합니다. 세 번째는 날짜/시간 범위 값의 부호를 변경할 수 있습니다.  
  
 피연산자 중 하나가 null이 고, 결과의 상태 면 `COleDateTimeSpan` 값은 null입니다.  
  
 피연산자 중 하나가 잘못 되었으며 다른은 null로, 하는 경우 결과의 상태 `COleDateTimeSpan` 값이 올바르지 않습니다.  
  
 유효 하 고, 잘못 된 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  COleDateTimeSpan::operator + =, =  
 더하기 및 빼기는 `COleDateTimeSpan` 값이 `COleDateTimeSpan` 값입니다.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>설명  
 이러한 연산자를 사용 하면 추가 하 고이 날짜/시간 범위 값을 뺄 `COleDateTimeSpan` 개체입니다. 피연산자 중 하나가 null이 고, 결과의 상태 면 `COleDateTimeSpan` 값은 null입니다.  
  
 피연산자 중 하나가 잘못 되었으며 다른은 null로, 하는 경우 결과의 상태 `COleDateTimeSpan` 값이 올바르지 않습니다.  
  
 유효 하 고, 잘못 된 null 상태 값에 대 한 자세한 내용은 참조는 [m_status](#m_status) 멤버 변수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>  Double COleDateTimeSpan::operator  
 이 변환 `COleDateTimeSpan` 값을 한 **double**합니다.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>설명  
 이 값을 반환 하는이 연산자 `COleDateTimeSpan` 일도 부동 소수점 숫자 값입니다.  
  
##  <a name="setdatetimespan"></a>  COleDateTimeSpan::SetDateTimeSpan  
 이 날짜/시간 범위 값의 값을 설정 합니다.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 이 개체로 복사할 날짜 범위 및 시간 범위 값을 나타내는 `COleDateTimeSpan` 개체입니다.  
  
### <a name="remarks"></a>설명  
 값을 쿼리 하는 함수는 `COleDateTimeSpan` 개체는 다음 멤버 함수를 참조 하십시오.  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>  COleDateTimeSpan::SetStatus  
 이 상태 (유효성) 설정 `COleDateTimeSpan` 개체입니다.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *status*  
 새 상태 값이 `COleDateTimeSpan` 개체입니다.  
  
### <a name="remarks"></a>설명  
 *상태* 으로 매개 변수 값이 정의 **DateTimeSpanStatus** 열거 형식 내에 정의 된는 `COleDateTimeSpan` 클래스입니다.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 에 대 한 간략 한 설명은이 상태 값을 다음 목록을 참조 합니다.  
  
- **COleDateTimeSpan::valid** 나타냅니다가 `COleDateTimeSpan` 개체는 유효 합니다.  
  
- **COleDateTimeSpan::invalid** 나타냅니다가 `COleDateTimeSpan` 개체가 잘못 되었습니다; 즉, 해당 값 올바르지 않을 수 있습니다.  
  
- **COleDateTimeSpan::null** 나타냅니다가 `COleDateTimeSpan` 개체가 null 인 경우 즉,이 개체에 대해 제공 된 값입니다. (이 c + +와 달리 "값이 없는 것"의 데이터베이스 의미에서 "null" **NULL**.)  
  
    > [!CAUTION]
    >  이 함수는 고급 프로그래밍 시나리오에 사용 합니다. 이 함수는이 개체에서 데이터를 변경 하지 않습니다. 상태를 설정 하 여 가장 자주 사용 됩니다 `null` 또는 **잘못 된**합니다. 할당 연산자 ( [연산자 =](#eq)) 및 [SetDateTimeSpan](#setdatetimespan) 원본 값에 따라 개체의 상태를 설정지 않습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATLMFC_Utilities#22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [COleDateTime 클래스](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime 클래스](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan 클래스](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)


