---
title: "CStringElementTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CStringElementTraits<T>
- ATL::CStringElementTraits<T>
- CStringElementTraits
- ATL.CStringElementTraits
- ATL::CStringElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f46ff072bcd0f772dac1bba52b114d82ee433112
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraits-class"></a>CStringElementTraits 클래스
이 클래스는 저장 하는 컬렉션 클래스에서 사용 하는 정적 함수를 제공 `CString` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색에 사용할 데이터 형식입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(정적) 두 문자열 요소가 같은지 비교 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(정적) 두 문자열 요소를 비교 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::CopyElements](#copyelements)|(정적) 복사 하려면이 함수를 호출 `CString` 컬렉션 클래스 개체에 저장 된 요소입니다.|  
|[CStringElementTraits::Hash](#hash)|(정적) 지정 된 문자열 요소에 대 한 해시 값을 계산 하려면이 함수를 호출 합니다.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(정적) 위치를 다시 지정 하려면이 함수를 호출 `CString` 컬렉션 클래스 개체에 저장 된 요소입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 복사, 이동 및 문자열을 비교 하 고 해시 값을 만들기 위한 정적 함수를 제공 합니다. 이러한 함수는 문자열 기반 데이터를 저장 하는 컬렉션 클래스를 사용 하는 경우에 유용 합니다. 사용 하 여 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) 대/소문자 구분 비교는 필요 합니다. 사용 하 여 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 때는 문자열 개체는 참조로 처리할 수 있습니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cstringt.h  
  
##  <a name="a-namecompareelementsa--cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements  
 두 문자열 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>매개 변수  
 `str1`  
 첫 번째 요소는 문자열입니다.  
  
 `str2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false 그렇지 않으면 true를 반환 합니다.  
  
##  <a name="a-namecompareelementsordereda--cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>매개 변수  
 `str1`  
 첫 번째 요소는 문자열입니다.  
  
 `str2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열이 동일 하면 0이 할당 < 0="" if=""> `str1` 는 보다 작은 `str2`, 또는 > 0 경우 `str1` 보다 크면 `str2`합니다. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행 하는 데 사용 됩니다.  

  
##  <a name="a-namecopyelementsa--cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements  
 이 정적 함수를 복사 하려면 호출 `CString` 컬렉션 클래스 개체에 저장 된 요소입니다.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDest`  
 복사한 데이터를 받을 첫 번째 요소에 대 한 포인터입니다.  
  
 `pSrc`  
 복사할 첫 번째 요소에 대 한 포인터입니다.  
  
 `nElements`  
 복사할 요소의 수입니다.  
  
### <a name="remarks"></a>주의  
 원본 및 대상 요소 겹치지 않아야 합니다.  
  
##  <a name="a-namehasha--cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Hash  
 지정된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 문자열 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열의 내용을 사용 하 여 계산 된 해시 값을 반환 합니다.  
  
##  <a name="a-nameinargtypea--cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 컬렉션 클래스 개체에서 요소를 검색에 사용할 데이터 형식입니다.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="a-namerelocateelementsa--cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 이 정적 함수를 재배치할 호출 `CString` 컬렉션 클래스 개체에 저장 된 요소입니다.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDest`  
 위치가 변경 된 데이터를 받을 첫 번째 요소에 대 한 포인터입니다.  
  
 `pSrc`  
 재배치 하는 첫 번째 요소에 대 한 포인터입니다.  
  
 `nElements`  
 재배치 하는 요소 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 정적 함수를 호출 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), 대부분의 데이터 형식에 대 한 충분 한 합니다. 이동 되는 개체에서 해당 멤버에 대 한 포인터를 포함 하는 경우이 정적 함수를 재정의할 수 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CElementTraitsBase 클래스](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI 클래스](../../atl/reference/cstringelementtraitsi-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

