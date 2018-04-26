---
title: add_volatile 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d66f7c315fe406a7ac7cbcb3abe706ae702cdf13
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="addvolatile-class"></a>add_volatile 클래스

지정된 형식에서 휘발성 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

`add_volatile<T>`의 인스턴스에는 *T*가 참조, 함수 또는 휘발성 한정 형식인 경우 *T*, 아닌 경우 `volatile` *T*인 멤버 typedef `type`이 있습니다. `add_volatile_t` 별칭은 멤버 typedef `type`에 액세스하기 위한 바로 가기입니다.

## <a name="example"></a>예제

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)<br/>
