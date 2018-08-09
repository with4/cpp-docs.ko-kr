---
title: 'Makeallocator:: Allocate 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs:
- C++
helpviewer_keywords:
- Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3252096216757c34e93933bcdd91f9da2c5bb14f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015971"
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate 메서드
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>반환 값  
 성공 하면 할당된 된 메모리;에 대 한 포인터 그렇지 않으면 **nullptr**합니다.  
  
## <a name="remarks"></a>설명  
 메모리를 할당 하 고 현재 연결 **MakeAllocator** 개체입니다.  
  
 할당된 된 메모리의 크기는 현재 지정 된 형식의 크기 **MakeAllocator** 템플릿 매개 변수입니다.  
  
 개발자만 재정의 해야 합니다 **Allocate()** 다른 메모리 할당 모델을 구현 하는 방법입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [MakeAllocator 클래스](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)