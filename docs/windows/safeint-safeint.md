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
ms.openlocfilehash: c7154349105c1953ad314b7928e7be8385179c42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
`SafeInt` 개체를 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
  
#### <a name="parameters"></a>매개 변수  
 [in] `i`  
 새 `SafeInt` 개체의 값입니다. 이 생성자에 따라 T 또는 U 형식의 매개 변수여야 합니다.
  
  
 [in] `b`  
 새 `SafeInt` 개체의 부울 값입니다.  
  
 [in] `u`  
U 형식의 `SafeInt`입니다. 새 `SafeInt` 개체는 T 형식의 u와 같은 값입니다.
  
 U  
 `SafeInt`에 저장되는 데이터 형식입니다. 부울, 문자 또는 정수 형식이 될 수 있습니다. 데이터 형식이 정수 형식인 경우 부호가 없거나 있을 수도 있으며 8비트에서 64비트 사이여야 합니다.  
  
## <a name="remarks"></a>설명  
 템플릿 형식 `T` 및 `E`에 대한 자세한 내용은 [SafeInt 클래스](../windows/safeint-class.md)를 참조합니다.
  
 생성자에 대해 입력된 매개 변수인 `i` 혹은 `u`는 부울, 문자 또는 정수 형식이어야 합니다. 매개 변수가 다른 형식인 경우 `SafeInt` 클래스는 [static_assert](../cpp/static-assert.md)를 호출하여 잘못된 입력 매개변수를 알려줍니다.  
  
 서식 파일 유형을 사용 하는 생성자 `U` 자동으로 입력된 매개 변수에서 지정한 형식으로 변환 `T`합니다. `SafeInt` 클래스는 데이터의 손실 없이 변환합니다. 데이터 손실 없이 T 형식으로 변환할 수 없는 경우 오류처리기 E에 보고합니다. 오류 처리기로 보고 `E` 데이터 형식으로 변환할 수 없으면 `T` 데이터 손실 없이 합니다.  
  
 부울 매개변수로 `SafeInt`를 생성하는 경우 값을 바로 초기화해야 합니다. `SafeInt` 코드를 통해 `SafeInt<bool> sb;`를 만들 수 없습니다. 이를 시도하면 컴파일 에러가 발생합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)
