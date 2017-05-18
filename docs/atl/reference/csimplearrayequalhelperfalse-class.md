---
title: "CSimpleArrayEqualHelperFalse 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
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
ms.openlocfilehash: cd5ed7058194880ef1ceaebe788e3deb60d4ac8e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse 클래스
이 클래스는에 대 한 도우미는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생된 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(정적) False를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 이 특성 클래스는 보완 하는 `CSimpleArray` 클래스입니다. 반환 false, 또한 호출 하 항상을 it `ATLASSERT` 적으로 참조 되는 경우 false 인수를 사용 합니다. 이 클래스를 대부분 메서드에 대 한 제대로 작동 하지만 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식으로 실패 하는 요소를 포함 하는 배열을 사용 하면 같음 테스트가 되지 충분히 정의 되어 없는 경우에서 [CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 false를 반환합니다.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>반환 값  
 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 항상 false를 반환 하며 호출 합니다 `ATLASSERT` 한 인수로 참조 하는 경우 false를 반환 합니다. 목적은 `CSimpleArrayEqualHelperFalse::IsEqual` 비교를 사용 하 여 같음 테스트 적절 하 게 정의 하지 않은 경우에 잘 정의 된 방식으로 실패 하는 메서드를 적용 하는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleArrayEqualHelper 클래스](../../atl/reference/csimplearrayequalhelper-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

