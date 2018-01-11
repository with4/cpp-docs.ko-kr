---
title: "MixIn 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::MixIn
dev_langs: C++
helpviewer_keywords: MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 883e952dde579cce3f5a65ba4a453f98ddbb4740
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mixin-structure"></a>MixIn 구조체
런타임 클래스가 Windows 런타임 인터페이스에서 파생되었는지 확인한 다음 있는 경우 클래식 COM 인터페이스를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Derived`  
 파생 된 형식에서 [구현](../windows/implements-structure.md) 구조입니다.  
  
 `MixInType`  
 기본 형식입니다.  
  
 `hasImplements`  
 `true`이 현재 구현 기본 형식으로 파생되면 `MixInType`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 Windows 런타임과 클래스 COM 인터페이스에서 파생 된 클래스는 클래스 선언 목록 다른 모든 Windows 런타임 인터페이스를 먼저 나열 되어야 하 고 모든 클래식 COM 인터페이스입니다. MixIn는 인터페이스가 올바른 순서로 지정되는지 확인합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `MixIn`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)