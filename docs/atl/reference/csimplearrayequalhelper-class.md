---
title: "CSimpleArrayEqualHelper 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
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
ms.openlocfilehash: 4a87879683257c66de5fe4e720dd29fa4c47031d
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper 클래스
이 클래스는에 대 한 도우미는 [CSimpleArray](../../atl/reference/csimplearray-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생된 클래스입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(정적) 두 `CSimpleArray` 개체 같음에 대 한 요소입니다.|  
  
## <a name="remarks"></a>주의  
 이 특성 클래스는 보완은 `CSimpleArray` 클래스입니다. 에 저장 된 두 요소를 비교에 대 한 메서드를 제공 된 `CSimpleArray` 개체입니다. 사용 하는 요소를 비교 하는 기본적으로 **operator=()**, 배열에 자신의 같음 연산자가 없는 복잡 한 데이터 형식을 포함 하는 경우이 클래스를 재정의 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 두 `CSimpleArray` 개체 같음에 대 한 요소입니다.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>매개 변수  
 *t1*  
 T. 형식의 개체  
  
 *t&2;*  
 T. 형식의 개체  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false 그렇지 않으면 true를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleArray 클래스](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse 클래스](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

