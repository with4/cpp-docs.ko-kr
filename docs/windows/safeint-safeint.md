---
title: 'Safeint:: Safeint | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9820227384866cdb1a6470ebd9650187848334c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
 새 `SafeInt` 개체의 값입니다. 이 생성자에 따라 T 또는 U 형식의 매개 변수 여야합니다.  
  
 [in] `b`  
 새 `SafeInt` 개체의 부울 값입니다.  
  
 [in] `u`  
 U 형식의 `SafeInt` 입니다. 새 `SafeInt` 개체는 T형식의 u와 같은 값입니다.
  
 U  
 `SafeInt`에 저장되는 데이터 형식입니다. 부울, 문자 또는 정수 형식이 될 수 있습니다. 데이터 형식이 정수 형식인 경우 부호가 없거나 있을 수도 있으며 8 비트에서 64 비트 사이여야 합니다.
  
## <a name="remarks"></a>설명  
 템플릿 형식 `T` 및 `E`에 대한 자세한 내용은 [SafeInt 클래스](../windows/safeint-class.md)를 참조합니다.
  
 생성자에 대한 입력된 매개 변수인 `i` 혹은 `u`는 부울, 문자 또는 정수 형식 이어야 합니다. 매개 변수를 다른 형식인 경우 `SafeInt` 클래스는 [static_assert](../cpp/static-assert.md)를 호출하여 잘못된 입력 매개변수를 알려줍니다.
  
 템플릿 U 형식을 사용하는 생성자는 입력된 매개 변수를 지정된 T 형식으로 자동 변환합니다. `SafeInt` 클래스는 데이터의 손실 없이 변환 합니다. 데이터 손실없이 T 형식으로 변환할 수 없는 경우 오류처리기 E에 보고합니다.
  
 부울 매개변수로 `SafeInt`를 생성하는 경우 값을 바로 초기화 해야 합니다. `SafeInt<bool> sb;` 코드를 통해 `SafeInt`를 만들 수 없습니다. 이렇게 시도한다면 컴파일 에러를 발생시킵니다.
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)
