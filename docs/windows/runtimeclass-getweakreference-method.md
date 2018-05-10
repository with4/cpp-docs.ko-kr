---
title: 'Runtimeclass:: Getweakreference 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs:
- C++
helpviewer_keywords:
- GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e49703e96728e7287206aa264ce12deaad611495
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="runtimeclassgetweakreference-method"></a>RuntimeClass::GetWeakReference 메서드
현재 RuntimeClass 개체에 대 한 약한 참조 개체에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDMETHOD(  
   GetWeakReference  
)(_Deref_out_ IWeakReference **weakReference);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `weakReference`  
 이 작업이 완료 될 때, 약한 참조 개체에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 항상 S_OK입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [RuntimeClass 클래스](../windows/runtimeclass-class.md)