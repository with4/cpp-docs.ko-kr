---
title: 'Chaininterfaces:: Fillarraywithiid 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bd9f899457c3a6045d7a5525c9fb560e23f10d3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461038"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>ChainInterfaces::FillArrayWithIid 메서드
인터페이스 ID가 정의한 저장소 합니다 *I0* 인터페이스 Id의 지정된 된 배열에 지정된 된 위치에 템플릿 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 *index*  
 에 인덱스 값에 대 한 포인터를 *iid* 배열입니다.  
  
 *iid*  
 인터페이스 Id의 배열입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)