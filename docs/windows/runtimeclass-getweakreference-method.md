---
title: "Runtimeclass:: Getweakreference 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetWeakReference
dev_langs: C++
helpviewer_keywords: GetWeakReference method
ms.assetid: 26656ace-7f20-4364-87c9-4a75dd30912e
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba87fe5097f9aff52b54770c1d438be2be425259
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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