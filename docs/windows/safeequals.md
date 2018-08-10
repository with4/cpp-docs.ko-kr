---
title: SafeEquals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeEquals
dev_langs:
- C++
helpviewer_keywords:
- SafeEquals function
ms.assetid: 6019627d-f170-413b-9abd-2b5b34396a72
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 510d5490cdd400465c2743f194dc698daf9e1e55
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018161"
---
# <a name="safeequals"></a>SafeEquals
같은지 여부를 확인 하려면 두 숫자를 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename T, typename U>  
inline bool SafeEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *t*  
 비교할 첫 번째 숫자입니다. T 형식이어야 합니다.  
  
 [in] *u*  
 비교할 두 번째 숫자입니다. U 형식이어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 하는 경우 *t* 하 고 *u* 같고, 그렇지 않으면 **false**합니다.  
  
## <a name="remarks"></a>설명  
 메서드를 향상 시킵니다 `==` 하므로 **SafeEquals** 두 가지 유형의 숫자를 비교할 수 있습니다.  
  
 이 메서드는 부분 [SafeInt 라이브러리](../windows/safeint-library.md) 의 인스턴스를 만들지 않고 단일 비교 작업에 대 한 설계 되는 [SafeInt 클래스](../windows/safeint-class.md)합니다.  
  
> [!NOTE]
>  이 메서드는 단일 수학 연산을 보호해야 하는 경우에만 사용해야 합니다. 작업이 여러 개 있으면 개별 독립 실행형 함수를 호출하는 대신 `SafeInt` 클래스를 사용해야 합니다.  
  
 템플릿 형식 T 및 U에 대 한 자세한 내용은 참조 하세요. [SafeInt 함수](../windows/safeint-functions.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** microsoft:: utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 함수](../windows/safeint-functions.md)   
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeNotEquals](../windows/safenotequals.md)