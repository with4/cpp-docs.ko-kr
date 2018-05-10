---
title: 'Hstringreference:: Operator = = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
dev_langs:
- C++
ms.assetid: cad3d52d-cd67-4194-a270-5239b1121a09
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 32cb8898cfc26297aaea888f9a382b5901ef8acf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator== 연산자
두 개의 매개 변수가 같은지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline bool operator==(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lhs`  
 비교할 첫 번째 매개 변수입니다. `lhs`는 HStringReference 개체 또는 HSTRING 핸들일 수 있습니다.  
  
 `rhs`  
 비교할 두 번째 매개 변수입니다.  `rhs`는 HStringReference 개체 또는 HSTRING 핸들일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 경우는 `lhs` 및 `rhs` 같고, 그렇지 않으면 매개 변수는 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)