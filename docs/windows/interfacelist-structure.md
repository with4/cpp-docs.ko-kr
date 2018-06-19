---
title: InterfaceList 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52acf2f0b9936903b4359e21e23ae50c95d2f31a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876737"
---
# <a name="interfacelist-structure"></a>InterfaceList 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 인터페이스 이름입니다. 재귀 목록에서 첫 번째 인터페이스입니다.  
  
 `U`  
 인터페이스 이름입니다. 재귀 목록에서 나머지 인터페이스입니다.  
  
## <a name="remarks"></a>설명  
 인터페이스의 재귀 목록을 만드는 데 사용.  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|`FirstT`|템플릿 매개 변수에 대 한 동의어 `T`합니다.|  
|`RestT`|템플릿 매개 변수에 대 한 동의어 `U`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `InterfaceList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)