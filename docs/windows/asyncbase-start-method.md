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
ms.openlocfilehash: 0acc6f62530daf641a2e4d568ed511d6fd831c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860920"
---
# <a name="asyncbasestart-method"></a>AsyncBase::Start 메서드
비동기 작업을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>반환 값  
 S_ok이 고 작업을 시작 하거나 이미 있으면 시작 됨 그렇지 않으면 E_ILLEGAL_STATE_CHANGE 합니다.  
  
## <a name="remarks"></a>설명  
 Start (), IAsyncInfo::Start의 기본 구현을 이며 실제로 진행 되지 않습니다. 실제로 비동기 작업을 시작 하려면 onstart () 순수 가상 메서드를 재정의 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)