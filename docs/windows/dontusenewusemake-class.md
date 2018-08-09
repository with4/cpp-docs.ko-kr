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
ms.openlocfilehash: 32418b163cb31f5eaf20c9d2b3ff3a4b585850dd
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644101"
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake 클래스
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>설명  
 연산자를 사용 하는 것을 금지 **새** 에서 `RuntimeClass`합니다. 결과적으로 사용 해야 합니다 [함수](../windows/make-function.md) 대신 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[DontUseNewUseMake::operator 새 연산자](../windows/dontusenewusemake-operator-new-operator.md)|연산자 오버 로드 **새** 에서 사용 되지 않도록 방지 하 고 `RuntimeClass`입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make 함수](../windows/make-function.md)