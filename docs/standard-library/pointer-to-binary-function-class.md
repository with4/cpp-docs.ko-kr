---
title: "pointer_to_binary_function 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::pointer_to_binary
- pointer_to_binary
dev_langs:
- C++
helpviewer_keywords:
- pointer_to_binary_function function
- pointer_to_binary_function class
ms.assetid: fb50599f-bcb3-4076-a669-6dcc3eb189a5
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: a510056f33bce7720896e56c7ea7798729dd831a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/19/2017

---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function 클래스
이항 함수 포인터를 조정 가능한 이항 함수로 변환합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Arg1, class Arg2, class Result>
class pointer_to_binary_function
    : public binary_function <Arg1, Arg2, Result>
{
public:
    explicit pointer_to_binary_function(
        Result(*pfunc)(Arg1, Arg2));
    Result operator()(Arg1 left, Arg2 right) const;
};
```  
  
#### <a name="parameters"></a>매개 변수  
 `pfunc`  
 변환할 이진 함수입니다.  
  
 `left`  
 *\*pfunc*를 호출한 왼쪽 개체입니다.  
  
 `right`  
 *\*pfunc*를 호출한 오른쪽 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 템플릿 클래스는 **pfunc**의 복사본을 저장합니다. 그리고 해당 구성원 함수 `operator()`가 (\* **pfunc**)(_ *Left*, \_ *Right*)를 반환하는 것으로 정의합니다.  
  
## <a name="remarks"></a>설명  
 이진 함수 포인터는 함수 개체이며, 매개 변수로 이진 함수를 사용해야 하는 C++ 표준 라이브러리 알고리즘으로 전달할 수는 있지만 조정할 수는 없습니다. 이진 함수 포인터에 값을 바인딩하거나 이 포인터를 부정자와 함께 사용하는 경우와 같이 이진 함수 포인터를 어댑터와 함께 사용하려면 이러한 조정을 가능하도록 하는 중첩 형식 **first_argument_type**, **second_argument_type** 및 **result_type**을 포인터에 제공해야 합니다. `pointer_to_binary_function`을 사용하여 변환을 수행하면 함수 어댑터를 이진 함수 포인터와 함께 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 `pointer_to_binary_function`의 생성자는 직접 사용되는 경우가 거의 없습니다. `pointer_to_binary_function` 어댑터 조건자를 선언하고 사용하는 방법의 예제는 도우미 함수 [ptr_fun](../standard-library/functional-functions.md#ptr_fun)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<functional>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




