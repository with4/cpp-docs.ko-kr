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
ms.openlocfilehash: de7ffb304a8b2f1567ed5510c276c454903ec930
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608406"
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
 *lhs*  
 비교할 첫 번째 매개 변수입니다. *lhs* 에 대 한 참조 수를 **HString**합니다.  
  
 *rhs*  
 비교할 두 번째 매개 변수입니다. *rhs* 에 대 한 참조 수를 **HString**합니다.  
  
## <a name="return-value"></a>반환 값  
 **true** 경우는 *lhs* 매개 변수는 보다 작은 *rhs* 매개 변수가 고, 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)