---
title: "CElementTraitsBase 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a06af7698afb24c1c2391b762673c7e3633018d4
ms.lasthandoff: 02/24/2017

---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase 클래스
이 클래스는 기본 복사본을 제공 하며 메서드는 컬렉션 클래스를 이동 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색에 사용할 데이터 형식입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|컬렉션 클래스 개체에 저장 된 요소를 복사 하려면이 메서드를 호출 합니다.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|컬렉션 클래스 개체에 저장 된 요소의 위치를 다시 지정 하려면이 메서드를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 기본 클래스를 복사 및 재배치 컬렉션 클래스에는 요소는 메서드를 정의 합니다. 클래스에 의해 사용 되는 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), 및 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 컬렉션 클래스 개체에 저장 된 요소를 복사 하려면이 메서드를 호출 합니다.  
  
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
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 컬렉션에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 컬렉션에서 요소를 검색에 사용할 데이터 형식입니다.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 컬렉션 클래스 개체에 저장 된 요소의 위치를 다시 지정 하려면이 메서드를 호출 합니다.  
  
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
 이 메서드는 호출 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), 대부분의 데이터 형식에 대 한 충분 한 합니다. 이동 되는 개체에서 해당 멤버에 대 한 포인터를 포함 하는 경우이 메서드를 재정의할 수 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

