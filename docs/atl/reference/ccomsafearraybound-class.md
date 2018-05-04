---
title: CComSafeArrayBound 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 455e71cd0ee323df8cfe43001f87179c649eefe5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound 클래스
이 클래스는에 대 한 래퍼는 [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d) 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|생성자입니다.|  
|[GetCount](#getcount)|요소의 수를 반환 하려면이 메서드를 호출 합니다.|  
|[GetLowerBound](#getlowerbound)|하한값을 반환 하려면이 메서드를 호출 합니다.|  
|[GetUpperBound](#getupperbound)|상한 값을 반환 하려면이 메서드를 호출 합니다.|  
|[SetCount](#setcount)|요소의 수를 설정 하려면이 메서드를 호출 합니다.|  
|[SetLowerBound](#setlowerbound)|하한값을 설정 하려면이 메서드를 호출 합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator =](#operator_eq)|설정 된 `CComSafeArrayBound` 를 새 값입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는에 대 한 래퍼는 **SAFEARRAYBOUND** 구조에서 사용 하는 [CComSafeArray](../../atl/reference/ccomsafearray-class.md)합니다. 쿼리 및 단일 차원의 상한 및 하 한 범위를 설정 하기 위해 메서드를 제공는 `CComSafeArray` 개체 및 포함 된 요소의 수입니다. 다차원 `CComSafeArray` 개체 배열을 사용 하 여 `CComSafeArrayBound` 개체, 각 차원에 대 한 합니다. 따라서와 같은 메서드를 사용 하는 경우 [GetCount](#getcount)을 알아야이 메서드는 다차원 배열에서 요소의 총 수를 반환 하지 것입니다.  
  
 **헤더:** atlsafe.h  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound  
 생성자입니다.  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ulCount`  
 배열의 요소 수입니다.  
  
 `lLowerBound`  
 배열의 번호가 매겨진 하한값입니다.  
  
### <a name="remarks"></a>설명  
 배열이 Visual c + + 프로그램에서 액세스 해야 하는 경우 하한값 0으로 정의 하는 것이 좋습니다. Visual Basic과 같은 다른 언어에서 사용 되는 배열이 다른 하 한 값을 사용 하는 것이 좋습니다 수도 있습니다.  
  
##  <a name="getcount"></a>  CComSafeArrayBound::GetCount  
 요소의 수를 반환 하려면이 메서드를 호출 합니다.  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 요소의 수를 반환합니다.  
  
### <a name="remarks"></a>설명  
 하는 경우 연결 된 `CComSafeArray` 개체가 나타내는 다차원 배열,이 메서드는 오른쪽에 있는 차원에 있는 요소의 총 수를 반환만 합니다. 사용 하 여 [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) 요소의 총 수를 가져올 수 있습니다.  
  
##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound  
 하한값을 반환 하려면이 메서드를 호출 합니다.  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 하 한을 반환 된 `CComSafeArrayBound` 개체입니다.  
  
##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound  
 상한 값을 반환 하려면이 메서드를 호출 합니다.  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 한 상한을 반환는 `CComSafeArrayBound` 개체입니다.  
  
### <a name="remarks"></a>설명  
 상한 요소 및 하 한 값의 수에 따라 달라 집니다. 예를 들어 하 한은 0 이며 요소 수가 10, 상한은 9로 자동으로 설정 됩니다.  
  
##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =  
 설정 된 `CComSafeArrayBound` 를 새 값입니다.  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bound`  
 `CComSafeArrayBound` 개체입니다.  
  
 `ulCount`  
 요소의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터를 반환 합니다.는 `CComSafeArrayBound` 개체입니다.  
  
### <a name="remarks"></a>설명  
 `CComSafeArrayBound` 기존를 사용 하 여 개체를 할당할 수 `CComSafeArrayBound`, 하거나 기본적으로 경우 하한값을 0으로 설정 된 요소 수를 제공 합니다.  
  
##  <a name="setcount"></a>  CComSafeArrayBound::SetCount  
 요소의 수를 설정 하려면이 메서드를 호출 합니다.  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ulCount`  
 요소의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 에 있는 요소의 수를 반환 합니다.는 `CComSafeArrayBound` 개체입니다.  
  
##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound  
 하한값을 설정 하려면이 메서드를 호출 합니다.  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lLowerBound`  
 하 한입니다.  
  
### <a name="return-value"></a>반환 값  
 새 하한값을 반환 된 `CComSafeArrayBound` 개체입니다.  
  
### <a name="remarks"></a>설명  
 배열이 Visual c + + 프로그램에서 액세스 해야 하는 경우 하한값 0으로 정의 하는 것이 좋습니다. Visual Basic과 같은 다른 언어에서 사용 되는 배열이 다른 하 한 값을 사용 하는 것이 좋습니다 수도 있습니다.  
  
 상한 요소 및 하 한 값의 수에 따라 달라 집니다. 예를 들어 하 한은 0 이며 요소 수가 10, 상한은 9로 자동으로 설정 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
