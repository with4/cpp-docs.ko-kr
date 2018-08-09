---
title: 'Comptrref:: Comptrref 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef, constructor
ms.assetid: ce2d2533-fef6-4b2d-b088-6f3db01df5a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 621f852728cb40ea88a916b37147c28d8bb0db38
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644464"
---
# <a name="comptrrefcomptrref-constructor"></a>ComPtrRef::ComPtrRef 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
ComPtrRef(  
   _In_opt_ T* ptr  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *ptr*  
 다른 기본 값 **ComPtrRef** 개체입니다.  
  
## <a name="remarks"></a>설명  
 새 인스턴스를 초기화 합니다 **ComPtrRef** 지정 된 포인터를 클래스 **ComPtrRef** 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [ComPtrRef 클래스](../windows/comptrref-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)