---
title: add_const 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_const
dev_langs:
- C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e79c06c49c8245da4911e8b72020537aa2e7bb45
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="addconst-class"></a>add_const 클래스

형식에서 const 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>매개 변수

`Ty` 수정할 형식입니다.

## <a name="remarks"></a>설명

`Ty`가 참조, 함수 또는 const 한정 형식인 경우 형식 한정자 인스턴스는 수정된 형식인 `Ty`이고, 그렇지 않은 경우 `const Ty`입니다.

## <a name="example"></a>예제

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const 클래스](../standard-library/remove-const-class.md)<br/>
