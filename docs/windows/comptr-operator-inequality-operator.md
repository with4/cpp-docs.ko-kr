---
title: "Comptr:: Operator! = 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2610061fcb7266ae5457935d680f7bce82797c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptroperator-operator"></a>ComPtr::operator!= 연산자
두 ComPtr 개체가 같지 않은지를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `a`  
 ComPtr 개체에 대 한 참조입니다.  
  
 `b`  
 다른 ComPtr 개체에 대 한 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 첫 번째 연산자 수확량 `true` 경우 개체 `a` 개체과 같지 않은 `b`, 그렇지 않으면 `false`합니다.  
  
 두 번째 및 세 번째 연산자에서 생성 `true` 경우 개체 `a` 과 같지 않은 `nullptr`, 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft:: wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [ComPtr 클래스](../windows/comptr-class.md)