---
title: WeakRef::operator&amp; 연산자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c8221b405618b1879f4e4c865115a227eb09857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890118"
---
# <a name="weakrefoperatoramp-operator"></a>WeakRef::operator&amp; 연산자
현재 WeakRef 개체를 나타내는 ComPtrRef 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>반환 값  
 현재 WeakRef 개체를 나타내는 ComPtrRef 개체입니다.  
  
## <a name="remarks"></a>설명  
 사용자 코드에서 사용할 수를 고려 하지 않은 내부 도우미 연산자입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)