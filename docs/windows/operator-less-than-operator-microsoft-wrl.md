---
title: "연산자&lt; 연산자 (microsoft:: wrl) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::operator<
dev_langs: C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d82291702791b138e0aaebefb5650e19d9e515f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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
 `true`하는 경우의 주소 `a` 의 주소 보다 작으면 `b`, 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)