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
ms.openlocfilehash: 57ad76b48b92519eaeed089dfb14817c38273588
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856162"
---
# <a name="cloakediid-structure"></a>CloakedIid 구조체
IID 목록에서 지정된 인터페이스가 액세스할 수 없는 RuntimeClass, Implements 및 ChainInterfaces 템플릿에 대해 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 인터페이스는 숨겨진 (숨김)입니다.  
  
## <a name="remarks"></a>설명  
 다음은 CloakedIid 사용 되는 방법의 예: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)