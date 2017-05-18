---
title: "CComQIPtrElementTraits 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: d6405cc3ec04988d0e0d7dd9a98f22c271b3608d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits 클래스
이 클래스는 COM 인터페이스 포인터의 컬렉션을 만들 때 메서드, 정적 함수 및 형식 정의가 유용 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>매개 변수  
 `I`  
 저장에 대 한 포인터의 유형을 지정 하는 COM 인터페이스입니다.  
  
 `piid`  
 에 대 한 포인터의 IID `I`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 메서드를 파생 하 고의 컬렉션 클래스를 만들 때 유용한 형식 정의 제공 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 인터페이스 포인터 개체입니다. 이 클래스는 둘 다에서 사용 되는 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 및 [CInterfaceList](../../atl/reference/cinterfacelist-class.md) 클래스입니다.  
  
 자세한 내용은 참조 [ATL 컬렉션 클래스](../../atl/atl-collection-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcoll.h  
  
##  <a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE  
 컬렉션 클래스 개체에 요소를 추가 하는 데 사용 하 여 데이터 형식입니다.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>참고 항목  
 [CDefaultElementTraits 클래스](../../atl/reference/cdefaultelementtraits-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

