---
title: CFileTimeSpan 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: facf4abc01ed55ec7c6d84755530a776c68e166d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan 클래스
이 클래스는 상대 날짜 및 시간 값의 파일 연결을 관리 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|호출에서 시간 범위를 검색 하려면이 메서드는 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|호출의 시간 범위를 설정 하려면이 메서드는 `CFileTimeSpan` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|에 대해 빼기를 수행 합니다.는 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::operator! =](#operator_neq)|두 `CFileTimeSpan` 개체가 다른지 비교합니다.|  
|[CFileTimeSpan::operator +](#operator_add)|에 대해 더하기를 수행 합니다.는 `CFileTimeSpan` 개체입니다.|  
|[CFileTimeSpan::operator + =](#operator_add_eq)|에 대해 더하기를 수행 합니다.는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.|  
|[CFileTimeSpan::operator &lt;](#operator_lt)|두 `CFileTimeSpan` 중 더 작은 값을 결정 하는 개체입니다.|  
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|두 `CFileTimeSpan` 같음 여부 또는 더 작은 값을 결정 하는 개체입니다.|  
|[CFileTimeSpan::operator =](#operator_eq)|대입 연산자입니다.|  
|[-= CFileTimeSpan::operator](#operator_-_eq)|에 대해 빼기를 수행 합니다.는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.|  
|[CFileTimeSpan::operator = =](#operator_eq_eq)|두 `CFileTimeSpan` 개체가 같은지 비교합니다.|  
|[CFileTimeSpan::operator &gt;](#operator_gt)|두 `CFileTimeSpan` 더 큰 숫자를 확인 하는 개체입니다.|  
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|두 `CFileTimeSpan` 같음 여부 또는 더 큰 숫자를 확인 하는 개체입니다.|  
  
## <a name="remarks"></a>설명  
 상대적 기간을 관리 하기 위한 메서드를 제공 하는이 클래스는 시기와 관련 된 작업을 수행할 때 자주 발생 하는 시간은 파일을, 마지막으로 액세스 한 만들거나 마지막으로 수정 합니다. 이 클래스의 메서드는 자주 사용 하는와 함께에서 [CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md) 개체입니다.  
  
## <a name="example"></a>예제  
 예를 참조 [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atltime.h  
  
##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan  
 생성자입니다.  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 기존 `CFileTimeSpan` 개체입니다.  
  
 `nSpan`  
 기간 (밀리초)입니다.  
  
### <a name="remarks"></a>설명  
 `CFileTimeSpan` 기존를 사용 하 여 개체를 만들 수 `CFileTimeSpan` 개체, 또는 64 비트 값으로 표현 합니다. 기본 생성자는 시간 범위를 0으로 설정 합니다.  
  
##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan  
 호출에서 시간 범위를 검색 하려면이 메서드는 `CFileTimeSpan` 개체입니다.  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 밀리초의 시간 범위를 반환합니다.  
  
##  <a name="operator_-"></a>  CFileTimeSpan::operator-  
 에 대해 빼기를 수행 합니다.는 **CFileTimeSpan** 개체입니다.  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTimeSpan` 두 시간 범위 차이의 결과 나타내는 개체입니다.  
  
##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =  
 두 `CFileTimeSpan` 개체가 다른지 비교합니다.  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 비교 되는 항목에 같은지는 `CFileTimeSpan` 개체; 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_add"></a>  CFileTimeSpan::operator +  
 에 대해 더하기를 수행 합니다.는 `CFileTimeSpan` 개체입니다.  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `CFileTimeSpan` 걸쳐 있는 총 두 개의 시간이 들어 있는 개체입니다.  
  
##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator + =  
 에 대해 더하기를 수행 합니다.는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTimeSpan` 걸쳐 있는 총 두 개의 시간이 들어 있는 개체입니다.  
  
##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;  
 두 `CFileTimeSpan` 중 더 작은 값을 결정 하는 개체입니다.  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 작으면 첫 번째 개체 (즉, 더 짧은 기간을 나타냄), 두 번째 인스턴스보다 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=  
 두 `CFileTimeSpan` 같음 여부 또는 더 작은 값을 결정 하는 개체입니다.  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 첫 번째 개체 (즉, 더 짧은 기간을 나타냄) 보다 작은 경우 또는 그렇지 않으면 값이 고 두 번째 **false**합니다.  
  
##  <a name="operator_eq"></a>  CFileTimeSpan::operator =  
 대입 연산자입니다.  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTimeSpan` 개체입니다.  
  
##  <a name="operator_-_eq"></a>  -= CFileTimeSpan::operator  
 에 대해 빼기를 수행 합니다.는 `CFileTimeSpan` 개체를 현재 개체에 결과 할당 합니다.  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CFileTimeSpan` 개체입니다.  
  
##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator = =  
 두 `CFileTimeSpan` 개체가 같은지 비교합니다.  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 는 개체가 같을 경우, 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;  
 두 `CFileTimeSpan` 더 큰 숫자를 확인 하는 개체입니다.  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 첫 번째 개체 보다 큰 경우 (즉, 긴 시간 간격을 나타냄), 두 번째 인스턴스보다 그렇지 않으면 **false**합니다.  
  
##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=  
 두 `CFileTimeSpan` 같음 여부 또는 더 큰 숫자를 확인 하는 개체입니다.  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `span`  
 비교할 `CFileTimeSpan` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 첫 번째 개체 보다 큰 경우 (즉, 긴 시간 간격을 나타냄) 또는 그렇지 않으면 값이 고 두 번째 **false**합니다.  
  
##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan  
 호출의 시간 범위를 설정 하려면이 메서드는 `CFileTimeSpan` 개체입니다.  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nSpan`  
 밀리초의 시간 범위에 대 한 새 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime 클래스](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)


