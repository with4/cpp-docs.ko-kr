---
title: EnableIf 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
dev_langs:
- C++
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 014099ce3e9152d2402263baaa6d6b30607756ed
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644975"
---
# <a name="enableif-structure"></a>EnableIf 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   bool b,  
   typename T = void  
>  
  
struct EnableIf;  
template <  
   typename T  
>  
struct EnableIf<true, T>;  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 형식입니다.  
  
 *b*  
 부울 식입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 템플릿 매개 변수를 평가 하는 경우 두 번째 템플릿 매개 변수로 지정 된 형식의 데이터 멤버를 정의 **true**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`type`|경우 템플릿 매개 변수 *b* 로 평가 **true**, 데이터 멤버를 정의 하는 부분 특수화 `type` 형식으로 `T`입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `EnableIf`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)