---
title: allocator&lt;void&gt; 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::allocator<void>
- allocator<void>
dev_langs:
- C++
helpviewer_keywords:
- allocator<void> class
ms.assetid: abfb40f5-c600-46a6-b130-f42c6535b2bd
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1bc3128b81aa1ea10c1c147d1d1c1f7d5bb8550
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="allocatorltvoidgt-class"></a>allocator&lt;void&gt; 클래스

`void` 형식에 대한 템플릿 클래스 할당자의 특수화로, 이 컨텍스트에 맞는 형식을 정의합니다.

## <a name="syntax"></a>구문

```cpp
template <>
class allocator<void> {
    typedef void *pointer;
    typedef const void *const_pointer;
    typedef void value_type;
    template <class Other>
    struct rebind;
    allocator();
    allocator(const allocator<void>&);

    template <class Other>
    allocator(const allocator<Other>&);

    template <class Other>
    allocator<void>& operator=(const allocator<Other>&);
};
```

## <a name="remarks"></a>설명

이 클래스는 *void* 형식에 대한 [allocator](../standard-library/allocator-class.md) 템플릿 클래스를 명시적으로 특수화합니다. 해당 생성자 및 대입 연산자는 템플릿 클래스에 대해 동일하게 동작하지만 다음 형식만 정의합니다.

- [const_pointer](../standard-library/allocator-class.md#const_pointer).

- [pointer](../standard-library/allocator-class.md#pointer).

- [value_type](../standard-library/allocator-class.md#value_type).

- [rebind](../standard-library/allocator-class.md#rebind), 중첩된 템플릿 클래스.

## <a name="requirements"></a>요구 사항

**헤더:** \<memory>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
