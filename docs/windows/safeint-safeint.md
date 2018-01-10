---
title: 'Safeint:: Safeint | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs: C++
helpviewer_keywords: SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: "7"
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
 새 값 `SafeInt` 개체입니다. 이 생성자에 따라 T 또는 U, 형식의 매개 변수 여야 합니다.  
  
 [in] `b`  
 새 부울 값 `SafeInt` 개체입니다.  
  
 [in] `u`  
 A `SafeInt` 형식 u 새 `SafeInt` 개체와 같은 값을 갖습니다 `u`는 T 형식 이어야 하지만  
  
 U  
 에 저장 된 데이터의 종류는 `SafeInt`합니다. 이 부울, 문자 또는 정수 형식 수 있습니다. 데이터 형식이 정수 형식인 경우 서명 하거나 이동할 수 있습니다 부호 없는 8 및 64 비트 사이 여야 합니다.  
  
## <a name="remarks"></a>설명  
 템플릿 형식에 대 한 자세한 내용은 `T` 및 `E`, 참조 [SafeInt 클래스](../windows/safeint-class.md)합니다.  
  
 생성자에 대 한 입력된 매개 변수 `i` 또는 `u`, 부울, 문자 또는 정수 형식 이어야 합니다. 매개 변수를 다른 형식인 경우는 `SafeInt` 클래스가 호출 [static_assert](../cpp/static-assert.md) 잘못 된 입력된 매개 변수를 나타냅니다.  
  
 서식 파일 유형을 사용 하는 생성자 `U` 자동으로 입력된 매개 변수에서 지정한 형식으로 변환 `T`합니다. `SafeInt` 클래스는 데이터의 손실 없이 데이터를 변환 합니다. 오류 처리기로 보고 `E` 데이터 형식으로 변환할 수 없으면 `T` 데이터 손실 없이 합니다.  
  
 만드는 경우는 `SafeInt` 부울 매개 변수에서 값을 즉시 초기화 해야 합니다. 생성할 수 없습니다 한 `SafeInt` 코드를 사용 하 여 `SafeInt<bool> sb;`합니다. 이 인해 컴파일 오류가 생성 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>참고 항목  
 [SafeInt 라이브러리](../windows/safeint-library.md)   
 [SafeInt 클래스](../windows/safeint-class.md)   
 [SafeIntException 클래스](../windows/safeintexception-class.md)