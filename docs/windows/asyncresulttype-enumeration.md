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
ms.openlocfilehash: de4a8465dd61e52425a0335e171cf516591ae589
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType 열거형
GetResults 메서드에서 반환되는 결과 형식을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`MultipleResults`|Close ()를 호출 하기 전에 그리고 시작 상태 간에 점진적으로 표시 되는 여러 결과 집합입니다.|  
|`SingleResult`|단일 결과 완료 이벤트가 발생 한 후 표시 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)