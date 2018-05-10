---
title: 'Runtimeclass:: Decrementreference 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::DecrementReference
dev_langs:
- C++
ms.assetid: f5ecfeaa-2865-455b-9208-94a0685fd2c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 660c78ba8a6b3000facc43541249fb6f9856a813
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclassdecrementreference-method"></a>RuntimeClass::DecrementReference 메서드
현재 RuntimeClass 개체에 대 한 참조 횟수를 감소 시킵니다.  
  
## <a name="syntax"></a>구문  
  
```  
ULONG DecrementReference();  
```  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)