---
title: "CAutoPtrElementTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
caps.latest.revision: 20
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
ms.openlocfilehash: 1c543eaa678d86e083207915bcb4f43766ee23c5
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits 클래스
이 클래스의 스마트 포인터 컬렉션을 만들 때 정적 함수 메서드와 유용한 형식 정의 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename T>  
class CAutoPtrElementTraits 
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```    
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 포인터 형식입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|컬렉션 클래스 개체에서 요소를 검색에 사용할 데이터 형식입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 스마트 포인터를 포함 하는 컬렉션 클래스 개체의 생성을 위한 메서드, 정적 함수 및 형식 정의 제공 합니다. 클래스 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 및 [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 에서 파생 `CAutoPtrElementTraits`합니다. 벡터 new 및 delete 연산자를 필요로 하는 스마트 포인터의 컬렉션을 작성 하는 경우 사용 하 여 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 대신 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoPtrElementTraits::INARGTYPE  
 컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoPtrElementTraits::OUTARGTYPE  
 컬렉션 클래스 개체에서 요소를 검색에 사용할 데이터 형식입니다.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>참고 항목  
 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

