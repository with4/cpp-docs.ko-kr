---
title: "CloakedIid 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c61e005759af9b5fde4bfff407ed502a41c22a72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cloakediid-structure"></a>CloakedIid 구조체
IID 목록에서 지정된 인터페이스가 액세스할 수 없는 RuntimeClass, Implements 및 ChainInterfaces 템플릿에 대해 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename T  
>  
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