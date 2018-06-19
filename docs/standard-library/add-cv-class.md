---
title: add_cv 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9825b690336acc8e93b0d404cc8335e5b27404b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33840591"
---
# <a name="addcv-class"></a>add_cv 클래스

형식에서 const volatile 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

*T*가 이미 cv 한정자를 가지고 있거나 참조 또는 함수인 경우가 아닌 한, 수정된 형식 `add_cv<T>`의 인스턴스에는 [add_volatile](../standard-library/add-volatile-class.md) 및 [add_const](../standard-library/add-const-class.md)에 의해 수정된 *T*에 해당하는 `type` 멤버 typedef가 있습니다.

`add_cv_t<T>` 도우미 형식은 `add_cv<T>` 멤버 typedef `type`에 액세스하기 위한 바로 가기입니다.

## <a name="example"></a>예제

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits > **Namespace:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const 클래스](../standard-library/remove-const-class.md)<br/>
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)<br/>
