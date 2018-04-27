---
title: mem_fun1_ref_t 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_ref_t class
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e6a209511201a5c4c851eee2b72a530c0003197
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="memfun1reft-class"></a>mem_fun1_ref_t 클래스

참조 인수를 사용하여 초기화할 때 단일 인수를 사용하는 **non_const** 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {
    explicit mem_fun1_ref_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type& left,
    Arg right) const;

};
```

### <a name="parameters"></a>매개 변수

`_Pm` 클래스의 멤버 함수에 대 한 포인터 **형식** 함수 개체를 변환할 수 있습니다.

`left` 개체는는 `_Pm` 에서 멤버 함수를 호출 합니다.

`right` 인수에 지정 되 고 `_Pm`합니다.

## <a name="return-value"></a>반환 값

조정 가능한 이항 함수입니다.

## <a name="remarks"></a>설명

템플릿 클래스는 `_Pm`의 복사본을 저장합니다. 이는 전용 멤버 개체에서 **Type** 클래스의 멤버 함수에 대한 포인터여야 합니다. 멤버 함수 정의 `operator()` 반환 하도록 ( **왼쪽**.\* `_Pm`) ( **오른쪽**).

## <a name="example"></a>예제

`mem_fun1_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
