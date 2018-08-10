---
title: 'Hstring:: Operator! = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs:
- C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3fabc0dcbbc31a1707d1823fb1ec49a53aca6d3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015877"
---
# <a name="hstringoperator-operator"></a>HString::Operator!= 연산자
두 매개 변수가 같지 않은지를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
inline bool operator!=( const HString& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HStringReference& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HStringReference& rhs) throw()  
  
inline bool operator!=( const HSTRING& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
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