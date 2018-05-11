---
title: IsBaseOfStrict 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db8f315c0589ceb7cd9411873152fe644985818e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 기본 형식입니다.  
  
 `Derived`  
 파생된 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 하나가 다른 형식의 기본 형식인지 테스트합니다.  
  
 첫 번째 템플릿은 산출할 수 있습니다는 기본 형식에서 파생 된 형식이 있는지 여부를 테스트 **true** 또는 **false**합니다. 두 번째 템플릿 형식에서 파생 됩니다 자체가 항상 생성 하는지 여부를 테스트 **false**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[IsBaseOfStrict::value 상수](../windows/isbaseofstrict-value-constant.md)|한 형식이 다른 형식의 기본 인지를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)