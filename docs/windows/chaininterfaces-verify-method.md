---
title: 'Chaininterfaces:: Verify 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c83479434a936f32fb0f7367d8cd02c6676c74e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860696"
---
# <a name="chaininterfacesverify-method"></a>ChainInterfaces::Verify 메서드
템플릿 매개 변수 `I0`-`I9`에 의해 정의된 각 인터페이스가 IUnknown 및/또는 IInspectable에서 상속하는지, `I0`이 `I1`부터 `I9`까지 상속하는지 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>설명  
 확인 작업이 실패하는 경우 `static_assert`에서 실패를 설명하는 오류 메시지를 내보냅니다.  
  
## <a name="remarks"></a>설명  
 템플릿 매개 변수 `I0` 및 `I1` 는 필수이고, 매개 변수 `I2`부터 `I9`는 선택사항입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)