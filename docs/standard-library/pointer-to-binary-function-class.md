---
title: pointer_to_binary_function 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::pointer_to_binary
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
ms.workload:
- cplusplus
ms.openlocfilehash: 3e43c5f906aa68480120df504b95152bbd346348
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="pointertobinaryfunction-class"></a>pointer_to_binary_function 클래스

이항 함수 포인터를 조정 가능한 이항 함수로 변환합니다.

## <a name="syntax"></a>구문

```cpp
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

### <a name="parameters"></a>매개 변수

`pfunc` 이진 함수 변환입니다.

`left` 왼쪽 개체는  *\*pfunc* 에서 호출 됩니다.

`right` 오른쪽 개체는  *\*pfunc* 에서 호출 됩니다.

## <a name="return-value"></a>반환 값

템플릿 클래스는 **pfunc**의 복사본을 저장합니다. 그리고 해당 구성원 함수 `operator()`가 (\* **pfunc**)(_ *Left*, \_ *Right*)를 반환하는 것으로 정의합니다.

## <a name="remarks"></a>설명

이진 함수 포인터는 함수 개체이며, 매개 변수로 이진 함수를 사용해야 하는 C++ 표준 라이브러리 알고리즘으로 전달할 수는 있지만 조정할 수는 없습니다. 이진 함수 포인터에 값을 바인딩하거나 이 포인터를 부정자와 함께 사용하는 경우와 같이 이진 함수 포인터를 어댑터와 함께 사용하려면 이러한 조정을 가능하도록 하는 중첩 형식 **first_argument_type**, **second_argument_type** 및 **result_type**을 포인터에 제공해야 합니다. `pointer_to_binary_function`을 사용하여 변환을 수행하면 함수 어댑터를 이진 함수 포인터와 함께 사용할 수 있습니다.

## <a name="example"></a>예제

`pointer_to_binary_function`의 생성자는 직접 사용되는 경우가 거의 없습니다. `pointer_to_binary_function` 어댑터 조건자를 선언하고 사용하는 방법의 예제는 도우미 함수 [ptr_fun](../standard-library/functional-functions.md#ptr_fun)을 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
