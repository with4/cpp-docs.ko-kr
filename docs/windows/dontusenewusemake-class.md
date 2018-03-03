---
title: "DontUseNewUseMake 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c09276fb761dcd1f2f5be78afa40606e262aa3e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>설명  
 연산자를 사용 하는 것을 금지 `new` RuntimeClass에 있습니다. 따라서 사용 해야 합니다는 [함수](../windows/make-function.md) 대신 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[DontUseNewUseMake::operator 새 연산자](../windows/dontusenewusemake-operator-new-operator.md)|연산자 오버 로드 `new` RuntimeClass에서 사용 되지 않도록 방지 합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make 함수](../windows/make-function.md)