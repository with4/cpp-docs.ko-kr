---
title: RemoveReference 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
dev_langs:
- C++
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbad73662688ce14607e7be52b2fcd5b1968c954
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="removereference-structure"></a>RemoveReference 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class T>  
struct RemoveReference;  
template<class T>  
struct RemoveReference<T&>;  
template<class T>  
struct RemoveReference<T&&>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 클래스 템플릿 매개 변수에서 참조 또는 rvalue 참조 특성을 제거합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`Type`|클래스 템플릿 매개 변수에 대 한 동의어입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `RemoveReference`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)