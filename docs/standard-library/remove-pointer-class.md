---
title: remove_pointer 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::remove_pointer
dev_langs:
- C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e1a3e1aacbb35984525ebf6d8dbd055a5cbf7b2
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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

`T` 수정할 형식입니다.

## <a name="remarks"></a>설명

`remove_pointer<T>`의 인스턴스는 `T1`가 `T`, `T1*`, `T1* const` 또는 `T1* volatile` 형식인 경우 수정된 형식인 `T1* const volatile`을 보관하며, 그렇지 않은 경우 `T`를 보관합니다.

## <a name="example"></a>예제

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
