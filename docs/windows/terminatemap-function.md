---
title: TerminateMap 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::TerminateMap
dev_langs:
- C++
helpviewer_keywords:
- TerminateMap function
ms.assetid: 1c314a61-da5d-49bb-ac44-c34ee3c23b66
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b4787fec0a6b4b9f55c500b66786372945d9a523
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890351"
---
# <a name="terminatemap-function"></a>TerminateMap 함수
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline bool TerminateMap(  
   _In_ ModuleBase *module,   
   _In_opt_z_ const wchar_t *serverName,   
    bool forceTerminate) throw()  
```  
  
## <a name="parameters"></a>매개 변수  
 `module`  
 A [모듈](../windows/module-class.md)합니다.  
  
 `serverName`  
 매개 변수로 지정 된 모듈의 클래스 팩터리 하위 집합의 이름을 `module`합니다.  
  
 `forceTerminate`  
 `true` 에 관계 없이 팩터리 클래스를 종료 하려면 활성 상태는 `false` 활성 상태 이면 모든 팩터리 클래스 팩터리를 종료 하지를 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 클래스는 모든 팩터리가 종료 되었습니다; 하는 경우 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 지정된 된 모듈의 클래스 팩터리를 종료합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)