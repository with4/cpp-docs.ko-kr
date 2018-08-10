---
title: 'Handlet:: Detach 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7bf4a6fab735708295a0ae229e7b47101ecc115b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648394"
---
# <a name="handletdetach-method"></a>HandleT::Detach 메서드
현재 연결을 끊습니다 **HandleT** 해당 기본 핸들에서 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>반환 값  
 기본 핸들입니다.  
  
## <a name="remarks"></a>설명  
 이 작업이 완료 되 면, 현재 **HandleT** 잘못 된 상태로 설정 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)