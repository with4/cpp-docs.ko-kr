---
title: "CSimpleMapEqualHelperFalse 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
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
ms.openlocfilehash: 68a08ffc0ba126c523a779e3d1a72217dead6235
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse 클래스
이 클래스는에 대 한 도우미는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(정적) 두 키가 같은지 테스트합니다.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(정적) False를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 이 특성 클래스는 보완은 `CSimpleMap` 클래스입니다. 에 포함 된 두 요소를 비교 하기 위한 방법을 제공는 `CSimpleMap` 개체, 특히 두 개의 값 요소 또는 두 가지 주요 요소입니다.  
  
 값 비교는 항상 false를 반환 하 고 또한를 호출 합니다 `ATLASSERT` 적으로 참조 되는 경우 false 인수를 사용 합니다. 이 클래스를 대부분의 메서드에서 올바르게 작동 하지만 실패와 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식에 키/값 쌍을 포함 하는 맵을 사용 하면 여기서 같음 테스트 정의 되지 않은 충분히 상황에서는 [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 두 키가 같은지 테스트합니다.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>매개 변수  
 `k1`  
 첫 번째 키입니다.  
  
 `k2`  
 두 번째 키입니다.  
  
### <a name="return-value"></a>반환 값  
 키가 같으면 false 그렇지 않으면 true를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)합니다.  
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 false를 반환합니다.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>반환 값  
 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 항상 false를 반환 하며 호출 합니다 `ATLASSERT` 적으로 참조 되는 경우 false 인수를 사용 합니다. 목적은 `CSimpleMapEqualHelperFalse::IsEqualValue` 비교를 사용 하 여 같음 테스트 적절 하 게 정의 하지 않은 경우에 잘 정의 된 방식으로 실패 하는 메서드를 적용 하는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleMapEqualHelper 클래스](../../atl/reference/csimplemapequalhelper-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

