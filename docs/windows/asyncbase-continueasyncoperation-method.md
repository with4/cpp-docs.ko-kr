---
title: 'Asyncbase:: Continueasyncoperation 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7b5d2b10b571a3517beab98eaa839d5c7fd86c2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460835"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>AsyncBase::ContinueAsyncOperation 메서드
비동기 작업을 계속 처리 해야 중단 되어야 하는지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>반환 값  
 **true** 비동기 작업의 현재 상태 이면 *시작*, 즉, 작업을 계속 해야 합니다. 그렇지 않으면 **false**, 즉, 작업을 중지 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)