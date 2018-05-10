---
title: '연산자&lt; 연산자 (microsoft:: wrl) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
dev_langs:
- C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cd3ea56386cadc638fd0234993ef6a8a0f5eb2be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="operatorlt-operator-microsoftwrl"></a>연산자&lt; 연산자 (microsoft:: wrl)
한 개체의 주소 다른 보다 작은 인지 여부를 확인 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<class T, class U>  
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();  
template<class T, class U>  
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();  
```  
  
#### <a name="parameters"></a>매개 변수  
 `a`  
 왼쪽 개체입니다.  
  
 `b`  
 오른쪽 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 하는 경우의 주소 `a` 의 주소 보다 작으면 `b`, 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)