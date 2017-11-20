---
title: "CStringRefElementTraits 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs: C++
helpviewer_keywords: CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 733fbfd1a215ecf9a19990e38d0d4f11be8bd560
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits 클래스
이 클래스와 관련 된 클래스 개체를 컬렉션에 저장 된 문자열 정적 함수를 제공 합니다. String 개체 참조로 처리 됩니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장할 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|두 개의 문자열 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|두 개의 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::Hash](#hash)|지정 된 string 요소에 대 한 해시 값을 계산 하기이 정적 함수를 호출 합니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 문자열을 비교 하 고 해시 값을 만들기 위한 정적 함수를 제공 합니다. 이러한 함수는 문자열 기반 데이터를 저장 하는 컬렉션 클래스를 사용 하는 경우에 유용 합니다. 와 달리 [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) 및 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` 하면는 `CString` 로 전달 될 인수를 **const CString &** 참조합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 두 개의 문자열 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `element1`  
 첫 번째 요소는 문자열입니다.  
  
 `element2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false를 반환 하지 않으면 true를 반환 합니다.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 두 개의 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `str1`  
 첫 번째 요소는 문자열입니다.  
  
 `str2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열이 동일한 경우 0이 고, < 0 경우 `str1` 는 보다 작은 `str2`, 또는 > 0 경우 `str1` 보다 크면 `str2`합니다. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) 는 비교를 수행 하려면 메서드를 사용 합니다.  
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 지정 된 string 요소에 대 한 해시 값을 계산 하기이 정적 함수를 호출 합니다.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 문자열 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열의 내용을 사용 하 여 계산 된 해시 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
