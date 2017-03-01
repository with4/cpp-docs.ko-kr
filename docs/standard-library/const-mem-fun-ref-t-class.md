---
title: "const_mem_fun_ref_t 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::const_mem_fun_ref_t
- const_mem_fun_ref_t
- std.const_mem_fun_ref_t
- xfunctional/std::const_mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: cb5fd219cb69b7cd6edd2d5eb5b9abd0ab819369
ms.lasthandoff: 02/24/2017

---
# <a name="constmemfunreft-class"></a>const_mem_fun_ref_t 클래스
참조 인수를 사용하여 초기화할 때 인수를 사용하지 않는 **const** 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Result, class Type>
class const_mem_fun_ref_t
 : public unary_function<Type, Result>  
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
 };
```  
  
#### <a name="parameters"></a>매개 변수  
 `Pm`  
 함수 개체로 변환할 **Type** 클래스의 멤버 함수 포인터입니다.  
  
 `left`  
 `Pm` 멤버 함수가 호출되는 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 조정 가능한 단항 함수입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스는 `Pm`의 복사본을 저장합니다. 이는 전용 멤버 개체에서 **Type** 클래스의 멤버 함수에 대한 포인터여야 합니다. 또한 해당 멤버 함수 `operator()`가 ( **left**.\* `Pm`)() **const**를 반환하는 것으로 정의합니다.  
  
## <a name="example"></a>예제  
 `const_mem_fun_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`는 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref_function)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




