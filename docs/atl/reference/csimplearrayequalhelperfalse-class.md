---
title: CSimpleArrayEqualHelperFalse 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a325da2edd4af8b8b0e6e965dc60df8c11bf8d30
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882860"
---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse 클래스
이 클래스는에 대 한 도우미는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 파생된 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(정적) False를 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 이 특성 클래스는을 보완 하는 `CSimpleArray` 클래스입니다. 반환 false 및 또한 호출 항상을 it `ATLASSERT` 참조 적이 없으면 false의 인수와 함께 합니다. 이 클래스는 같음 테스트 정의 되지 않은 충분히 경우 대부분의 메서드에 대해 제대로 작동 하지만 같은 비교에 의존 하는 방법에 대 한 잘 정의 된 방식으로 실패 하는 요소를 포함 하는 배열을 사용 하면 [CSimpleArray:: 찾을](../../atl/reference/csimplearray-class.md#find)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelperFalse::IsEqual  
 false를 반환합니다.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>반환 값  
 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 항상 false를 반환 하며 호출 `ATLASSERT` 인수로 참조 하는 경우 false입니다. 목적은 `CSimpleArrayEqualHelperFalse::IsEqual` 메서드 비교를 사용 하 여 같음 테스트 적절 하 게 정의 하지 않은 경우에 잘 정의 된 방식으로 실패 하는 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleArrayEqualHelper 클래스](../../atl/reference/csimplearrayequalhelper-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
