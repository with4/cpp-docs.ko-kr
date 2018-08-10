---
title: 'Safeint:: Safeint | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8cfc0085164cfc9d5f3c8691fb50e0b98f796b32
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015068"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
생성 된 **SafeInt** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *있나요*  
 새 값 **SafeInt** 개체입니다. 이 생성자에 따라 T 또는 U 형식의 매개 변수여야 합니다.
  
  
 [in] *b*  
 새 부울 값을 **SafeInt** 개체입니다.  
  
 [in] *u*  
 A **SafeInt** 형식 u 새 **SafeInt** 개체와 동일한 값을 갖습니다 *u*, T. 형식일 수는 있지만  
  
 U  
 에 저장 된 데이터 유형의 합니다 **SafeInt**합니다. 부울, 문자 또는 정수 형식이 될 수 있습니다. 데이터 형식이 정수 형식인 경우 부호가 없거나 있을 수도 있으며 8비트에서 64비트 사이여야 합니다.  
  
## <a name="remarks"></a>설명  
 템플릿 형식 `T` 및 `E`에 대한 자세한 내용은 [SafeInt 클래스](../windows/safeint-class.md)를 참조합니다.
  
 생성자에 대 한 입력된 매개 변수 *있습니까* 하거나 *u*, 부울, 문자 또는 정수 형식 이어야 합니다. 매개 변수의 다른 형식인 경우는 **SafeInt** 호출을 클래스 [static_assert](../cpp/static-assert.md) 잘못 된 입력된 매개 변수를 나타냅니다.  
  
 서식 파일 유형을 사용 하는 생성자 `U` 자동으로 입력된 매개 변수에서 지정한 형식으로 변환 `T`합니다. 합니다 **SafeInt** 클래스 데이터의 손실 없이 데이터를 변환 합니다. 오류 처리기로 보고 `E` 데이터 형식으로 변환할 수 없으면 `T` 데이터 손실 없이 합니다.  
  
 만드는 경우는 **SafeInt** 부울 매개 변수에서 값을 즉시 초기화 해야 합니다. 생성할 수 없습니다.는 **SafeInt** 코드를 사용 하 여 `SafeInt<bool> sb;`입니다. 이를 시도하면 컴파일 에러가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl:: utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)
