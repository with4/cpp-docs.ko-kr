---
title: RuntimeClassType 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassType
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassType enumeration
ms.assetid: d380712d-672e-4ea9-b7c5-cf9fa7dbb770
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 43ab0a738af4c6bc92d42c0884827b574946d2ea
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892405"
---
# <a name="runtimeclasstype-enumeration"></a>RuntimeClassType 열거형
유형을 지정 [RuntimeClass](../windows/runtimeclass-class.md) 지원 되는 인스턴스.  
  
## <a name="syntax"></a>구문  
  
```  
enum RuntimeClassType;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`ClassicCom`|클래식 COM 런타임 클래스입니다.|  
|`Delegate`|에 해당 **ClassicCom**합니다.|  
|`InhibitFtmBase`|사용 하지 않도록 설정 `FtmBase` 하는 동안 지원 `__WRL_CONFIGURATION_LEGACY__` 정의 되어 있지 않습니다.|  
|`InhibitWeakReference`|약한 참조 지원을 해제합니다.|  
|`WinRt`|Windows 런타임 클래스입니다.|  
|`WinRtClassicComMix`|`WinRt` 및 `ClassicCom`의 조합입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)