---
title: "const_mem_fun1_ref_t 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 21d27d61880eb2e1841c7871c4ce82fb87de0b31
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t 클래스
참조 인수를 사용하여 초기화할 때 단일 인수를 사용하는 **const** 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Result, class Type, class Arg>
class const_mem_fun1_ref_t
 : public binary_function<Type, Arg, Result> 
 {
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
 };
```  
  
#### <a name="parameters"></a>매개 변수  
 `Pm`  
 함수 개체로 변환할 **Type** 클래스의 멤버 함수 포인터입니다.  
  
 `left`  
 `Pm` 멤버 함수가 호출되는 **const** 개체입니다.  
  
 `right`  
 `Pm`에 지정되는 인수입니다.  
  
## <a name="return-value"></a>반환 값  
 조정 가능한 이항 함수입니다.  
  
## <a name="remarks"></a>설명  
 템플릿 클래스는 `Pm`의 복사본을 저장합니다. 이는 전용 멤버 개체에서 **Type** 클래스의 멤버 함수에 대한 포인터여야 합니다. 또한 해당 멤버 함수 `operator()`가 ( `left`.\* *Pm*)( `right`) **const**를 반환하는 것으로 정의합니다.  
  
## <a name="example"></a>예  
 `const_mem_fun1_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`는 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법의 예제에 대해서는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)



