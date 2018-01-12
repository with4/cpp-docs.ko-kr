---
title: "CSimpleArrayEqualHelper 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs: C++
helpviewer_keywords: CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57e5b40785bda57a4d5578bb998c4c97336246be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>설명  
 이 특성 클래스는 적용 하기 위해는 `CSimpleArray` 클래스입니다. 에 저장 된 두 요소를 비교에 대 한 메서드를 제공는 `CSimpleArray` 개체입니다. 사용 하는 요소를 비교 하는 기본적으로 **operator=()**, 배열 자체 같음 연산자를 없는 복잡 한 데이터 형식이 있으면이 클래스를 재정의 해야 합니다.  
  
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
 화 형식의 개체  
  
 *t2*  
 화 형식의 개체  
  
### <a name="return-value"></a>반환 값  
 요소가 같은지, false를 반환 하지 않으면 true를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleArray 클래스](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse 클래스](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
