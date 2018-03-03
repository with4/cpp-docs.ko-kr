---
title: "is_nothrow_constructible 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02698c90714ae530e827d9bfbe6cdc7ce1fd0abf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible 클래스
지정된 인수 형식을 사용할 경우 형식이 생성 가능한지와 throw되지 않는 것으로 알려져 있는지를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 형식이 쿼리입니다.  
  
 `Args`  
 `T`의 생성자에서 일치시킬 인수 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `T` 형식이 `Args`의 인수 형식을 사용하여 생성 가능하고 생성자가 throw되지 않는 것으로 컴파일러에 알려진 경우 true이고, 그렇지 않으면 false입니다. 변수 정의 `T t(std::declval<Args>()...);`가 올바른 형식인 경우 `T` 형식은 생성 가능합니다. `T`와 `Args`의 모든 형식은 둘 다 완전한 형식이거나, `void`이거나, 범위를 알 수 없는 배열이어야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)



