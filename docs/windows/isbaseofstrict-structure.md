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
ms.openlocfilehash: d4690c15adac7be66ca916b1fc0f769e6c50190c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017905"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict 구조체
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
### <a name="parameters"></a>매개 변수  
 *자료*  
 기본 형식입니다.  
  
 *파생 된*  
 파생된 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 하나가 다른 형식의 기본 형식인지 테스트합니다.  
  
 첫 번째 템플릿 형식을 생성 하는 기본 형식에서 파생 됩니다 있는지 여부를 테스트 **true** 하거나 **false**합니다. 두 번째 템플릿은 파생 된 형식 자체에서 항상 생성 하는 여부를 테스트 **false**합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constants"></a>공용 상수  
  
|이름|설명|  
|----------|-----------------|  
|[IsBaseOfStrict::value 상수](../windows/isbaseofstrict-value-constant.md)|한 형식이 다른 형식의 기본 인지 여부를 나타냅니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)