---
title: 'Asyncbase:: Checkvalidstatefordelegatecall 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
dev_langs:
- C++
helpviewer_keywords:
- CheckValidStateForDelegateCall method
ms.assetid: d997ebe7-2378-4e74-a379-f0f85e6922f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a03f0dcb8f6d35c1d5fc8aec5bf1cc899d575861
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653074"
---
# <a name="asyncbasecheckvalidstatefordelegatecall-method"></a>AsyncBase::CheckValidStateForDelegateCall 메서드
현재 비동기 상태의 대리자 속성을 수정할 수 있는지 테스트 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline HRESULT CheckValidStateForDelegateCall();  
```  
  
## <a name="return-value"></a>반환 값  
 S_OK 대리자 속성을 수정할 수 있습니다. 그렇지 않으면 E_ILLEGAL_METHOD_CALL 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** async.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [AsyncBase 클래스](../windows/asyncbase-class.md)