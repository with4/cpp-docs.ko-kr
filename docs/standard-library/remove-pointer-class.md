---
title: remove_pointer 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::remove_pointer
dev_langs:
- C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9c8ddf5941394a8979832a753ed73cfda5f0876
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959126"
---
# <a name="removepointer-class"></a>remove_pointer 클래스

포인터부터 형식까지 다양한 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct remove_pointer;

template <class T>
using remove_pointer_t = typename remove_pointer<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

인스턴스의 `remove_pointer<T>` 는 형식인 수정 된 `T1` 때 *T* 의 형식은 `T1*`를 `T1* const`를 `T1* volatile`, 또는 `T1* const volatile`고, 그렇지 않으면 *T*합니다.

## <a name="example"></a>예

```cpp
#include <type_traits>
#include <iostream>

int main()
    {
    int *p = (std::remove_pointer_t<int *> *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "remove_pointer_t<int *> == "
        << typeid(*p).name() << std::endl;

    return (0);
    }
```

```Output
remove_pointer_t<int *> == int
```

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_pointer 클래스](../standard-library/add-pointer-class.md)<br/>
