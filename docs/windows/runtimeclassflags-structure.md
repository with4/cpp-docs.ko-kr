---
title: "RuntimeClassFlags 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85eb42c537845d86ce8cf3b1f20db7e9eeffe76f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 구조체
인스턴스에 대 한 형식을 포함 한 [RuntimeClass](../windows/runtimeclass-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 A [RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md) 값입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[RuntimeClassFlags::value 상수](../windows/runtimeclassflags-value-constant.md)|포함 된 [RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md) 값입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)