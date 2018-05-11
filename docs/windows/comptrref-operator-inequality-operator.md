---
title: 'Comptrref:: Operator! = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs:
- C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d5a6e7389215452177add30b587004c312aeae1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="comptrrefoperator-operator"></a>ComPtrRef::operator!= 연산자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `a`  
 ComPtrRef 개체에 대 한 참조입니다.  
  
 `b`  
 다른 ComPtrRef 개체 또는 익명 개체에 대 한 포인터에 대 한 참조 (`void*`).  
  
## <a name="return-value"></a>반환 값  
 첫 번째 연산자 수확량 `true` 경우 개체 `a` 개체과 같지 않은 `b`, 그렇지 않으면 `false`합니다.  
  
 두 번째 및 세 번째 연산자에서 생성 `true` 경우 개체 `a` 과 같지 않은 `nullptr`, 그렇지 않으면 `false`합니다.  
  
 네 번째와 다섯 번째 연산자에서 생성 `true` 경우 개체 `a` 개체과 같지 않은 `b`, 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 두 개의 ComPtrRef 개체가 같지 않은지 여부를 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [ComPtrRef 클래스](../windows/comptrref-class.md)