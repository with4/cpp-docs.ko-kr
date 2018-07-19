---
title: 'Hstring:: Operator&lt; 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
dev_langs:
- C++
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8fae7195f048cd680be513bd54b635e2e1e9bbf7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875112"
---
# <a name="hstringoperatorlt-operator"></a>Hstring:: Operator&lt; 연산자
첫 번째 매개 변수 인지 보다 작은 두 번째 매개 변수를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lhs`  
 비교할 첫 번째 매개 변수입니다. `lhs` HString에 대 한 참조를 수 있습니다.  
  
 `rhs`  
 비교할 두 번째 매개 변수입니다. `rhs` HString에 대 한 참조를 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 경우는 `lhs` 매개 변수는 보다 작은 `rhs` 매개 변수, 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)