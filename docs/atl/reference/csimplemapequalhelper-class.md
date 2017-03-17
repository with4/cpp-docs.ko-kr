---
title: "CSimpleMapEqualHelper 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ddb793889748446b9613c91ce6fcefe28da32eb3
ms.lasthandoff: 02/24/2017

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
 값 요소입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(정적) 두 키가 같은지 테스트합니다.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(정적) 두 값이 같은지를 테스트합니다.|  
  
## <a name="remarks"></a>주의  
 이 특성 클래스는 보완은 `CSimpleMap` 클래스입니다. 두 개를 비교 하기 위한 메서드를 제공 `CSimpleMap` 개체 같은지 요소 (특히, 키 및 값 구성 요소). 기본적으로 키와 값은 비교를 사용 하 여 `operator==()`, 자신의 같음 연산자가 없는 복잡 한 데이터 형식을 포함 하는 지도 하는 경우 필요한 추가 기능을 제공 하기이 클래스를 재정의할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
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
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 두 값이 같은지를 테스트합니다.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>매개 변수  
 *v1*  
 첫 번째 값입니다.  
  
 *v2*  
 두 번째 값입니다.  
  
### <a name="return-value"></a>반환 값  
 값이 같으면 false 그렇지 않으면 true를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSimpleMapEqualHelperFalse 클래스](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

