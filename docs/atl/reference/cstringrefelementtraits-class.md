---
title: "CStringRefElementTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 3709a5d4aac02651e5b6fafd441499fea1f8eabc
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits 클래스
이 클래스는 컬렉션 클래스 개체에 저장 된 문자열에 관련 된 정적 함수를 제공 합니다. String 개체 참조로 처리 됩니다.  
  
## <a name="syntax"></a>구문  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|두 문자열 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.|  
|[CStringRefElementTraits::Hash](#hash)|지정된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 문자열을 비교 하 고 해시 값을 만들기 위한 정적 함수를 제공 합니다. 이러한 함수는 문자열 기반 데이터를 저장 하는 컬렉션 클래스를 사용 하는 경우에 유용 합니다. 와 달리 [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) 및 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` 하면는 `CString` 로 전달 될 인수 **const CString < /** 참조 합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 두 문자열 요소가 같은지 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `element1`  
 첫 번째 요소는 문자열입니다.  
  
 `element2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false 그렇지 않으면 true를 반환 합니다.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 두 문자열 요소를 비교 하려면이 정적 함수를 호출 합니다.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `str1`  
 첫 번째 요소는 문자열입니다.  
  
 `str2`  
 두 번째 요소는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 문자열이 동일 하면 0이 할당 < 0="" if=""> `str1` 는 보다 작은 `str2`, 또는 > 0 경우 `str1` 보다 크면 `str2`합니다. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) 메서드는 비교를 수행 하는 데 사용 됩니다.  
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 지정된 문자열 요소에 대 한 해시 값을 계산 하려면이 정적 함수를 호출 합니다.  
  
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

