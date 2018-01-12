---
title: "CFileTime 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
dev_langs: C++
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d48e899bb058ed27559a4ef699a3a53267064f98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cfiletime-class"></a>CFileTime 클래스
이 클래스는 파일과 연결 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CFileTime :  public FILETIME
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTime::CFileTime](#cfiletime)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTime::GetCurrentTime](#getcurrenttime)|정적 검색 하려면이 함수 호출을 `CFileTime` 현재 시스템 날짜 및 시간을 나타내는 개체입니다.|  
|[CFileTime::GetTime](#gettime)|시간을 검색 하려면이 메서드를 호출 하는 `CFileTime` 개체입니다.|  
|[CFileTime::LocalToUTC](#localtoutc)|로컬 파일 시간에는 Utc (협정 세계시)를 기반으로 하는 파일 시간을 변환 하려면이 메서드를 호출 합니다.|  
|[CFileTime::SetTime](#settime)|날짜 및 시간에 의해 저장을 설정 하려면이 메서드를 호출 하는 `CFileTime` 개체입니다.|  
|[CFileTime::UTCToLocal](#utctolocal)|에 Utc (협정 세계시) 로컬 파일 시간을 기반으로 하는 시간을 변환 하려면이 메서드를 호출 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTime::operator-](#operator_-)|이 연산자를 사용에 빼기를 수행 하는 `CFileTime` 또는 `CFileTimeSpan` 개체입니다.|  
|[CFileTime::operator! =](#operator_neq)|이 연산자는 두 개의 비교 `CFileTime` 개체가 다른 지 비교 합니다.|  
|[CFileTime::operator +](#operator_add)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.|  
|[CFileTime::operator + =](#operator_add_eq)|이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.|  
|[CFileTime::operator&lt;](#operator_lt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.|  
|[CFileTime::operator&lt;=](#operator_lt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.|  
|[CFileTime::operator =](#operator_eq)|대입 연산자입니다.|  
|[-= CFileTime::operator](#operator_-_eq)|이 연산자를 사용에서 빼기를 수행 하는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.|  
|[CFileTime::operator = =](#operator_eq_eq)|이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.|  
|[CFileTime::operator&gt;](#operator_gt)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.|  
|[CFileTime::operator&gt;=](#operator_gt_eq)|이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.|  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTime::Day](#day)|정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.|  
|[CFileTime::Hour](#hour)|정적 데이터 멤버가 한 시간을 구성 하는 100 나노초 간격의 수를 저장 합니다.|  
|[CFileTime::Millisecond](#millisecond)|1 밀리초를 구성 하는 100 나노초 간격의 수를 저장 하는 정적 데이터 멤버가 있습니다.|  
|[CFileTime::Minute](#minute)|1 분을 구성 하는 100 나노초 간격의 수를 저장 하는 정적 데이터 멤버가 있습니다.|  
|[CFileTime::Second](#second)|1 초를 구성 하는 100 나노초 간격의 수를 저장 하는 정적 데이터 멤버가 있습니다.|  
|[CFileTime::Week](#week)|정적 데이터 멤버가 1 주일을 구성 하는 100 나노초 간격의 수를 저장 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 관련 생성, 액세스 및 파일을 수정 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다. 메서드 및이 클래스의 데이터와 함께에서 자주 사용 `CFileTimeSpan` 상대 시간 값을 처리 하는 개체입니다.  
  
 날짜 및 시간 값은 1601 년 1 월 1 일 이후 100 나노초 간격의 수를 나타내는 64 비트 값으로 저장 됩니다. Utc (협정 세계시) 형식입니다.  
  
 다음 정적 const 멤버 변수 계산을 단순화 하기 위해 제공 됩니다.  
  
|멤버 변수|100 나노초 간격의 수|  
|---------------------|-----------------------------------------|  
|Millisecond|10,000|  
|Second|밀리초 * 1, 000|  
|Minute|두 번째 * 60|  
|Hour|분 * 60|  
|Day|시간 * 24|  
|주|Day * 7|  
  
 **참고** 일부 파일 시스템에서 만들기를 기록할 수 있습니다 및 마지막 액세스 시간 및 모든 파일 시스템에 동일한 방식으로 기록 합니다. Windows NT FAT 파일 시스템에 예제 만들기에 대 한 시간 10 밀리초 해상도 쓰기 시간 2 초 해상도 및 액세스 시간 1 일 (액세스 날짜) 해상도 있습니다. Ntfs, 액세스 시간이 1 시간인 해상도 합니다. 또한 FAT 현지 시간으로 디스크에는 시간을 기록 하는 NTFS utc에서 시간 디스크에 기록 합니다. 자세한 내용은 참조 [파일 시간이](http://msdn.microsoft.com/library/windows/desktop/ms724290)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `FILETIME`  
  
 `CFileTime`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltime.h  
  
##  <a name="cfiletime"></a>CFileTime::CFileTime  
 생성자입니다.  
  
```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 A [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) 구조입니다.  
  
 `nTime`  
 날짜 및 64 비트 값으로 표현 된 시간입니다.  
  
### <a name="remarks"></a>설명  
 `CFileTime` 는 기존 날짜와 시간을 사용 하 여 개체를 만들 수는 `FILETIME` 구조, 또는 (로컬 또는 utc (협정 세계시) 시간 형식)에 64 비트 값으로 표현 합니다. 시간을 0으로 설정 하는 기본 생성자입니다.  
  
##  <a name="day"></a>CFileTime::Day  
 정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.  
  
```
static const ULONGLONG Day = Hour* 24;
```  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::Millisecond](#millisecond)합니다.  
  
##  <a name="getcurrenttime"></a>CFileTime::GetCurrentTime  
 정적 검색 하려면이 함수 호출을 `CFileTime` 현재 시스템 날짜 및 시간을 나타내는 개체입니다.  
  
```
static CFileTime GetCurrentTime() throw();
```  
  
### <a name="return-value"></a>반환 값  
 현재 시스템 날짜 및 시간을 utc (협정 세계시) 형식으로 반환합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]  
  
##  <a name="gettime"></a>CFileTime::GetTime  
 시간을 검색 하려면이 메서드를 호출 하는 `CFileTime` 개체입니다.  
  
```
ULONGLONG GetTime() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 로컬 또는 utc (협정 세계시) 형식 중 하나에 있을 수 있는 64 비트 숫자로 시간과 날짜를 반환 합니다.  
  
##  <a name="hour"></a>CFileTime::Hour  
 정적 데이터 멤버가 한 시간을 구성 하는 100 나노초 간격의 수를 저장 합니다.  
  
```
static const ULONGLONG Hour = Minute* 60;
```  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::Millisecond](#millisecond)합니다.  
  
##  <a name="localtoutc"></a>CFileTime::LocalToUTC  
 로컬 파일 시간에는 Utc (협정 세계시)를 기반으로 하는 파일 시간을 변환 하려면이 메서드를 호출 합니다.  
  
```
CFileTime LocalToUTC() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTime` UTC 형식으로 시간을 포함 하는 개체입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::UTCToLocal](#utctolocal)합니다.  
  
##  <a name="millisecond"></a>CFileTime::Millisecond  
 1 밀리초를 구성 하는 100 나노초 간격의 수를 저장 하는 정적 데이터 멤버가 있습니다.  
  
```
static const ULONGLONG Millisecond = 10000;
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]  
  
##  <a name="minute"></a>CFileTime::Minute  
 1 분을 구성 하는 100 나노초 간격의 수를 저장 하는 정적 데이터 멤버가 있습니다.  
  
```
static const ULONGLONG Minute = Second* 60;
```  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::Millisecond](#millisecond)합니다.  
  
##  <a name="operator_-"></a>CFileTime::operator-  
 이 연산자를 사용에 빼기를 수행 하는 `CFileTime` 또는 `CFileTimeSpan` 개체입니다.  
  
```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
 `ft`  
 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTime` 개체 또는 `CFileTimeSpan` 두 개체 사이의 시간 차이의 결과 나타내는 개체입니다.  
  
##  <a name="operator_neq"></a>CFileTime::operator! =  
 이 연산자는 두 개의 비교 `CFileTime` 개체가 다른 지 비교 합니다.  
  
```
bool operator!=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 비교할 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 되는 항목에 같은지는 `CFileTime` 개체, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_add"></a>CFileTime::operator +  
 이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하는 데 사용됩니다.  
  
```
CFileTime operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTime` 결과는 원래 시간 상대 시간을 나타내는 개체입니다.  
  
##  <a name="operator_add_eq"></a>CFileTime::operator + =  
 이 연산자는 `CFileTimeSpan` 개체에 대해 더하기를 수행하고 결과를 현재 개체에 할당하는 데 사용됩니다.  
  
```
CFileTime& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTime` 결과는 원래 시간 상대 시간을 나타내는 개체입니다.  
  
##  <a name="operator_lt"></a>CFileTime::operator&lt;  
 이 연산자는 두 `CFileTime` 개체를 비교하여 더 작은 값을 확인합니다.  
  
```
bool operator<(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 비교할 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 첫 번째 개체 (의 앞부분에 나오는 시간) 보다 작으면 두 번째 페이지인 **false** 그렇지 않은 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]  
  
##  <a name="operator_lt_eq"></a>CFileTime::operator&lt;=  
 이 연산자는 두 `CFileTime` 개체를 비교하여 더 작거나 같은 값을 확인합니다.  
  
```
bool operator<=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 비교할 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 그렇지 않으면 첫 번째 개체는 (이전 시간에서) 보다 작거나 같은 두 번째 경우 **false**합니다.  
  
##  <a name="operator_eq"></a>CFileTime::operator =  
 대입 연산자입니다.  
  
```
CFileTime& operator=(const FILETIME& ft) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 A `CFileTime` 새 시간 및 날짜를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTime` 개체입니다.  
  
##  <a name="operator_-_eq"></a>-= CFileTime::operator  
 이 연산자를 사용에서 빼기를 수행 하는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.  
  
```
CFileTime& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 A `CFileTimeSpan` 뺄 상대 시간을 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTime` 개체입니다.  
  
##  <a name="operator_eq_eq"></a>CFileTime::operator = =  
 이 연산자는 두 `CFileTime` 개체가 같은지 비교합니다.  
  
```
bool operator==(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 `CFileTime` 비교할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 는 개체가 같을 경우, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt"></a>CFileTime::operator&gt;  
 이 연산자는 두 `CFileTime` 개체를 비교하여 더 큰 값을 확인합니다.  
  
```
bool operator>(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 비교할 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** (시간) 뒷부분에서 첫 번째 개체는 보다 큰 경우, 두 번째 인스턴스보다 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt_eq"></a>CFileTime::operator&gt;=  
 이 연산자는 두 `CFileTime` 개체를 비교하여 더 크거나 같은 값을 확인합니다.  
  
```
bool operator>=(CFileTime ft) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ft`  
 비교할 `CFileTime` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 그렇지 않으면 첫 번째 개체는 두 번째 (의 뒷부분에 나오는 시간) 보다 크거나 경우 **false**합니다.  
  
##  <a name="second"></a>CFileTime::Second  
 정적 데이터 멤버가 하루를 구성 하는 100 나노초 간격의 수를 저장 합니다.  
  
```
static const ULONGLONG Second = Millisecond* 1000;
```  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::Millisecond](#millisecond)합니다.  
  
##  <a name="settime"></a>CFileTime::SetTime  
 날짜 및 시간에 의해 저장을 설정 하려면이 메서드를 호출 하는 `CFileTime` 개체입니다.  
  
```
void SetTime(ULONGLONG nTime) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nTime`  
 날짜와 현지 또는 utc (협정 세계시) 형식으로 시간을 나타내는 64 비트 값입니다.  
  
##  <a name="utctolocal"></a>CFileTime::UTCToLocal  
 에 Utc (협정 세계시) 로컬 파일 시간을 기반으로 하는 시간을 변환 하려면이 메서드를 호출 합니다.  
  
```
CFileTime UTCToLocal() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTime` 로컬 파일 시간 형식의 시간을 포함 하는 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]  
  
##  <a name="week"></a>CFileTime::Week  
 정적 데이터 멤버가 1 주일을 구성 하는 100 나노초 간격의 수를 저장 합니다.  
  
```
static const ULONGLONG Week = Day* 7;
```  
  
### <a name="example"></a>예  
 예를 참조 [CFileTime::Millisecond](#millisecond)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTimeSpan 클래스](../../atl-mfc-shared/reference/cfiletimespan-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)


