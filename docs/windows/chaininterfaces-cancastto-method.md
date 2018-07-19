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
ms.openlocfilehash: c2286c347fbd68f34fac807e80facca0a0286aa6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860296"
---
# <a name="chaininterfacescancastto-method"></a>ChainInterfaces::CanCastTo 메서드
지정 된 인터페이스 ID의 특수화는 기본이 아닌 템플릿 매개 변수에 의해 정의 된 각으로 캐스팅 될 수 있는지 여부를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
__forceinline bool CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `riid`  
 인터페이스 ID입니다.  
  
 `ppv`  
 성공적으로 캐스팅 된 마지막 인터페이스 ID에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 모든 캐스트 작업 성공 그렇지 않으면 `false`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)