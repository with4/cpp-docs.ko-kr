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
ms.openlocfilehash: 125ffe998e7c3f225f72e3fb47df4ef3525c37f9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649050"
---
# <a name="weakrefoperatoramp-operator"></a>WeakRef::operator&amp; 연산자
반환 된 `ComPtrRef` 현재를 나타내는 개체 **WeakRef** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>반환 값  
 A `ComPtrRef` 현재 나타내는 **WeakRef** 개체입니다.  
  
## <a name="remarks"></a>설명  
 코드에서 사용할 고려 하지 않은 한 내부 도우미 연산자입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [WeakRef 클래스](../windows/weakref-class.md)