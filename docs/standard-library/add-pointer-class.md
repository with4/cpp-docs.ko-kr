---
title: add_pointer 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7a80ffbfbcfb8c350eecc54e87c4cadaaab0295
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841420"
---
# <a name="addpointer-class"></a>add_pointer 클래스

지정된 형식에서 포인터-형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct add_pointer;

template <class T>
using add_pointer_t = typename add_pointer<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

`remove_reference<T>::type*`과 동일한 멤버 typedef `type` 이름입니다. `add_pointer_t` 별칭은 멤버 typedef `type`에 액세스하기 위한 바로 가기입니다.

참조에서 포인터를 만드는 것은 잘못이기 때문에 `add_pointer`가 포인터-형식을 만들기 전에 지정된 형식에서 참조(있는 경우)를 제거합니다. 결과적으로, 형식이 참조인지 걱정하지 않고도 `add_pointer`를 포함하여 형식을 사용할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 `add_pointer` 형식이 해당 형식의 포인터와 같은 경우를 보여 줍니다.

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_pointer_t<int> *p = (int **)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_pointer_t<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_pointer_t<int> == int *
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_pointer 클래스](../standard-library/remove-pointer-class.md)<br/>
