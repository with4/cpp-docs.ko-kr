---
title: 'Hstring:: Operator = = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
dev_langs:
- C++
ms.assetid: 77ff4c1a-e62a-4256-bf9d-0f017137c630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c21e9f79673cc888f8661803a8cc4bb9053870c4
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604566"
---
# <a name="hstringoperator-operator"></a>HString::Operator== 연산자
두 매개 변수가 같은지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline bool operator==(  
               const HString& lhs,   
               const HString& rhs) throw()  
  
inline bool operator==(  
                const HString& lhs,   
                const HStringReference& rhs) throw()  
  
inline bool operator==(  
                const HStringReference& lhs,   
                const HString& rhs) throw()  
  
inline bool operator==(  
                 const HSTRING& lhs,   
                 const HString& rhs) throw()  
  
inline bool operator==(  
                 const HString& lhs,   
                 const HSTRING& rhs) throw()  
```  
  
### <a name="parameters"></a>매개 변수  
 *lhs*  
 비교할 첫 번째 매개 변수입니다. *lhs* 수는 **HString** 또는 `HStringReference` 개체 또는 HSTRING 핸들입니다.  
  
 *rhs*  
 비교할 두 번째 매개 변수입니다. *rhs* 수는 **HString** 또는 `HStringReference` 개체 또는 HSTRING 핸들입니다.  
  
## <a name="return-value"></a>반환 값  
 **true** 경우는 *lhs* 하 고 *rhs* 매개 변수는 같고, 그렇지 않으면 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HString 클래스](../windows/hstring-class.md)