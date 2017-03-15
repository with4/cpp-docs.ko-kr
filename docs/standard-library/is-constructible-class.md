---
title: "is_constructible 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_constructible
- std.is_constructible
- std::is_constructible
- type_traits/std::is_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_constructible
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6c4a5d8e24f22a79a4bf442ab690f1b1dbdca580
ms.lasthandoff: 02/24/2017

---
# <a name="isconstructible-class"></a>is_constructible 클래스
지정된 인수 형식을 사용할 경우 형식이 생성 가능한지를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class... Args>  
struct is_constructible;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
 `Args`  
 `T`의 생성자에서 일치시킬 인수 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `T` 형식이 `Args`의 인수 형식을 사용하여 생성 가능한 경우 true이고, 그렇지 않으면 false입니다. 변수 정의 `T t(std::declval<Args>()...);`가 올바른 형식인 경우 `T` 형식은 생성 가능합니다. `T`와 `Args`의 모든 형식은 둘 다 완전한 형식이거나, `void`이거나, 범위를 알 수 없는 배열이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)




