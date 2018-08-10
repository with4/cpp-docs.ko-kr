---
title: 'Asyncbase:: Start 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32c59c00180b26a2856b1fc210302ffff0e72f0c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641306"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start 메서드
비동기 작업을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>반환 값  
 S_ok이 고, 작업을 시작 하거나 이미 있는 경우 시작 합니다. 그렇지 않으면 E_ILLEGAL_STATE_CHANGE 합니다.  
  
## <a name="remarks"></a>설명  
 **Start ()** 의 기본 구현 이며 `IAsyncInfo::Start`, 없습니다 실제 작업을 수행 합니다. 실제로 비동기 작업을 시작 하려면 재정의 `OnStart()` 순수 가상 메서드가 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)