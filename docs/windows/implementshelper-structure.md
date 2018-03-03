---
title: "ImplementsHelper 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper
dev_langs:
- C++
helpviewer_keywords:
- ImplementsHelper structure
ms.assetid: b857ba80-81bd-4e53-92b6-210991954243
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a51de59278e476be1e99b60ef1b0ab8a6e3f3cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelper-structure"></a>ImplementsHelper 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename RuntimeClassFlagsT,  
   typename ILst,  
   bool IsDelegateToClass  
>  
friend struct Details::ImplementsHelper;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `RuntimeClassFlagsT`  
 플래그의 하나 이상 지정 하는 필드 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거자입니다.  
  
 `ILst`  
 인터페이스 Id의 목록입니다.  
  
 `IsDelegateToClass`  
 지정 `true` 구현의 현재 인스턴스는 기본 클래스에 있는 첫 번째 인터페이스 ID의 경우 `ILst`, 그렇지 않으면 `false`합니다.  
  
## <a name="remarks"></a>설명  
 구현에 유용한는 [구현](../windows/implements-structure.md) 구조입니다.  
  
 이 템플릿은 인터페이스의 목록을 트래버스로 기본 클래스로 및 QueryInterface를 사용 하도록 설정 하는 데 필요한 정보로 추가 합니다.  
  
## <a name="members"></a>멤버  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ImplementsHelper`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [참조 (Windows 런타임 라이브러리)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)