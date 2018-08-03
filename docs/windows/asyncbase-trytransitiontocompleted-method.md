---
title: 'Asyncbase:: Trytransitiontocompleted 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
dev_langs:
- C++
helpviewer_keywords:
- TryTransitionToCompleted method
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2185b83a393860904903f4b82b3c3b42a2c3b33
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460744"
---
# <a name="asyncbasetrytransitiontocompleted-method"></a>AsyncBase::TryTransitionToCompleted 메서드
현재 비동기 작업이 완료 되었는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
bool TryTransitionToCompleted(  
   void  
);  
```  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 비동기 작업이 완료 되었으면;이 고, 그렇지 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)