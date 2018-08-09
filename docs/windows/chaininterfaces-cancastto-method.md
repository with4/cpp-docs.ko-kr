---
title: 'Chaininterfaces:: Cancastto 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 8be44875-53ed-494b-91a0-0f8e399685bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff24ac92e5e84cb85127ef6e33805928fabd6f60
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647533"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo 메서드
각 기본이 아닌 템플릿 매개 변수를 정의한 특수화에 지정 된 인터페이스 ID 캐스팅 될 수 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *riid*  
 인터페이스 ID입니다.  
  
 *ppv*  
 성공적으로 캐스팅 된 마지막 인터페이스 ID에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 모든 캐스트 작업이 성공 하면이 고, 그렇지 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)