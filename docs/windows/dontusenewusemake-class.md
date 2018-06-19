---
title: DontUseNewUseMake 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs:
- C++
helpviewer_keywords:
- DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f343d0b47d50cd375d186c29ff55b91898aa9c61
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872330"
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