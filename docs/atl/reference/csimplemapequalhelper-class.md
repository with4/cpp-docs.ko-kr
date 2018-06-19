---
title: CSimpleMapEqualHelper 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4bfef99d12ae724c2ca6e70375f08a8dc1fb15b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361842"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper 클래스
이 클래스는에 대 한 도우미는 [CSimpleMap](../../atl/reference/csimplemap-class.md) 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>매개 변수  
 `TKey`  
 핵심 요소입니다.  
  
 `TVal`  
 Value 요소입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(정적) 두 키가 같은지 테스트합니다.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(정적) 두 값이 같은지를 테스트합니다.|  
  
## <a name="remarks"></a>설명  
 이 특성 클래스는 적용 하기 위해는 `CSimpleMap` 클래스입니다. 두 개의 비교를 위한 메서드를 제공 `CSimpleMap` 개체 같은지 요소 (특히, 키 및 값 구성 요소). 기본적으로 키와 값 비교에 사용할 `operator==()`, 되지만 지도 자신의 같음 연산자를 없는 복잡 한 데이터 형식이 있으면이 클래스 필수 추가 기능을 제공 하기 재정의할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey  
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
 키가 같으면 false를 반환 하지 않으면 true를 반환 합니다.  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue  
 두 값이 같은지를 테스트합니다.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>매개 변수  
 *V1*  
 첫 번째 값입니다.  
  
 *V2*  
 두 번째 값입니다.  
  
### <a name="return-value"></a>반환 값  
 값이 같으면 false를 반환 하지 않으면 true를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleMapEqualHelperFalse 클래스](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
