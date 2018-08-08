---
title: 'Hstringreference:: Operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc8f919dcec994be5d4f0300e9c96dde95895e16
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608523"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator= 연산자
다른 값으로 이동 **HStringReference** 개체를 현재 **HStringReference** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
### <a name="parameters"></a>매개 변수  
 *other*  
 기존 **HStringReference** 개체입니다.  
  
## <a name="remarks"></a>설명  
 기존 값 *다른* 현재 개체를 복사할 **HStringReference** 개체를 차례로 합니다 *다른* 개체는 소멸 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HStringReference 클래스](../windows/hstringreference-class.md)