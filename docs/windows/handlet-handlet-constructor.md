---
title: 'Handlet:: Handlet 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a0bb864fa1356089552fb3c48461fef2a63920b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641381"
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT 생성자
새 인스턴스를 초기화 합니다 **HandleT** 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *h*  
 핸들입니다.  
  
## <a name="remarks"></a>설명  
 첫 번째 생성자는 초기화를 **HandleT** 개체 개체에 대 한 유효한 핸들입니다. 두 번째 생성자를 만듭니다 **HandleT** 매개 변수에서 개체 *h*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)