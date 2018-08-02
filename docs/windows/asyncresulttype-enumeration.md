---
title: AsyncResultType 열거형 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8171c4a57621a4f17a5f0ddb0745faa70fde6524
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465287"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 열거형
반환 된 결과의 형식을 지정 합니다 `GetResults()` 메서드.  
  
## <a name="syntax"></a>구문  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`MultipleResults`|간에 점진적으로 제공 되는 여러 결과 집합이 `Start` 상태 전과 `Close()` 라고 합니다.|  
|`SingleResult`|단일 결과 완료 이벤트가 발생 한 후 표시 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)