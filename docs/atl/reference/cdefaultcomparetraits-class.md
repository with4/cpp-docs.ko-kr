---
title: "CDefaultCompareTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
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
ms.openlocfilehash: 1d1253b7a7d69024465627cc9fb37fcd2afba693
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits 클래스
이 클래스는 기본 요소 비교 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 컬렉션에 저장 될 데이터의 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(정적) 두 요소가 같은지 비교 하려면이 함수를 호출 합니다.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(정적) 크고 작은 요소를 확인 하려면이 함수를 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 컬렉션 클래스 개체에 저장 된 요소를 비교 하기 위한 두 개의 정적 함수를 포함 합니다. 이 클래스에서 사용 되는 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)합니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 두 요소가 같은지 비교 하려면이 함수를 호출 합니다.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>매개 변수  
 `element1`  
 첫 번째 요소입니다.  
  
 `element2`  
 두 번째 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false 그렇지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 같음 ( `==`) 연산자. 단순 데이터 형식 이외의 개체의 경우이 함수를 재정의할 수 해야 합니다.  
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 크고 작은 요소를 확인 하려면이 함수를 호출 합니다.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>매개 변수  
 `element1`  
 첫 번째 요소입니다.  
  
 `element2`  
 두 번째 요소입니다.  
  
### <a name="return-value"></a>반환 값  
 다음 테이블을 기반으로 하는 정수를 반환 합니다.  
  
|조건|반환 값|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현을 사용 하는 `==`, ** \< **, 및 ** > ** 연산자입니다. 단순 데이터 형식 이외의 개체의 경우이 함수를 재정의할 수 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

