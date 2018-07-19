---
title: 'Asyncbase:: Cancel 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0559f32315265a7db5543e8559097177c2a670fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859854"
---
# <a name="asyncbasecancel-method"></a>AsyncBase::Cancel 메서드
비동기 작업을 취소합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>반환 값  
 기본적으로 항상 S_OK를 반환합니다.  
  
## <a name="remarks"></a>설명  
 Cancel (), IAsyncInfo::Cancel의 기본 구현을 이며 실제로 진행 되지 않습니다. 실제로 비동기 작업을 취소 하려면 OnCancel() 순수 가상 메서드를 재정의 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)