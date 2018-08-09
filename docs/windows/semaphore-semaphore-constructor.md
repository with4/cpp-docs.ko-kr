---
title: 'Semaphore:: semaphore 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore, constructor
ms.assetid: 91c22ae7-181e-460d-ad40-70c3a53b26fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13c0ded165e7c1510f0112d9b3b9e93f2e356775
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015600"
---
# <a name="semaphoresemaphore-constructor"></a>Semaphore::Semaphore 생성자
새 인스턴스를 초기화 합니다 **세마포** 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
explicit Semaphore(  
   HANDLE h  
);  
  
WRL_NOTHROW Semaphore(  
   _Inout_ Semaphore&& h  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *h*  
 핸들 또는 rvalue 참조에는 **세마포** 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers
 
 ## <a name="see-also"></a>참고 항목
 [Semaphore 클래스](../windows/semaphore-class.md)