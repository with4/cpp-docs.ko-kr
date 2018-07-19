---
title: remove_const 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_const
dev_langs:
- C++
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c0eaf8eeab1c5d9c024baa85af025f2294956e8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959286"
---
# <a name="removeconst-class"></a>remove_const 클래스

형식에서 비const 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct remove_const;
```

```cpp
template <class T>
using remove_const_t = typename remove_const<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

인스턴스의 `remove_const<T>` 는 형식인 수정 된 `T1` 때 *T* 형식인 `const T1`고, 그렇지 않으면 *T*합니다.

## <a name="example"></a>예

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_const_t<const int>*)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_const_t<const int> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_const_t<const int> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_const 클래스](../standard-library/add-const-class.md)<br/>
[remove_cv 클래스](../standard-library/remove-cv-class.md)<br/>
