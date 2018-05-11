---
title: ModuleType 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ModuleType
dev_langs:
- C++
helpviewer_keywords:
- ModuleType enumeration
ms.assetid: 61a763af-a5a4-451d-8b40-815af507fcde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d36355c9f64f9f5c827ef8c4d5b3cb6a77d17b65
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="moduletype-enumeration"></a>ModuleType 열거형
모듈이 in-process 서버를 지원하는지 out-of-process 서버를 지원해야 하는지 여부를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum ModuleType;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`InProc`|In-process 서버입니다.|  
|`OutOfProc`|Out-of-process 서버입니다.|  
|`DisableCaching`|모듈에 저장 하는 캐싱 메커니즘을 사용 하지 않도록 설정 합니다.|  
|`InProcDisableCaching`|조합의 `InProc` 및 `DisableCaching`합니다.|  
|`OutOfProcDisableCaching`|조합의 `OutOfProc` 및 `DisableCaching`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)