---
title: "Hstringreference:: Operator = 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 097e89ab4ae2d3b6ddaacb2fa52b811c1577ef72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 연산자
다른 HStringReference 개체의 값은 현재 HStringReference 개체를 이동합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### <a name="parameters"></a>매개 변수  
 `other`  
 기존 HStringReference 개체입니다.  
  
## <a name="remarks"></a>설명  
 기존 `other` 개체의 값은 현재 HStringReference 개체에 복사된 다음 `other` 개체가 소멸됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)