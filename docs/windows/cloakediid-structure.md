---
title: CloakedIid 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e0155006987165f5b192aac73bb31991081a231
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461225"
---
# <a name="cloakediid-structure"></a>CloakedIid 구조체
에 `RuntimeClass`, `Implements` 및 `ChainInterfaces` 지정된 된 인터페이스 IID 목록에서 액세스할 수 없는 템플릿.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>매개 변수  
 *T*  
 인터페이스는 숨겨진 (숨김)입니다.  
  
## <a name="remarks"></a>설명  
 다음은 방법의 예가 `CloakedIid` 는: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)