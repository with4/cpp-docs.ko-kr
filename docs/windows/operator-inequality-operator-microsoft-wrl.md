---
title: '연산자! = 연산자 (microsoft:: wrl) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator!=
dev_langs:
- C++
ms.assetid: 785435da-87a6-4454-9bce-9d288a96dc26
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 517184dffac0c35772e61284a18eca764fbb5cc8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603982"
---
# <a name="operator-operator-microsoftwrl"></a>operator!= Operator (Microsoft::WRL)
에 대 한 같지 않음 연산자 [ComPtr](../windows/comptr-class.md) 하 고 [ComPtrRef](../windows/comptrref-class.md) 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
WRL_NOTHROW bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
WRL_NOTHROW bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
WRL_NOTHROW bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
WRL_NOTHROW bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *a*  
 왼쪽 개체입니다.  
  
 *b*  
 오른쪽 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 없으면 개체가 같고, 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)