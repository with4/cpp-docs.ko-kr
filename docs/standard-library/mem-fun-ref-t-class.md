---
title: mem_fun_ref_t 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun_ref_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 029fba9cc5a13569df8cc1e2e11b639e65ea24c9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863906"
---
# <a name="memfunreft-class"></a>mem_fun_ref_t 클래스

참조 인수를 사용하여 초기화할 때 인수를 사용하지 않는 **non_const** 멤버 함수를 단항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;

};
```

### <a name="parameters"></a>매개 변수

`_Pm` 클래스의 멤버 함수에 대 한 포인터 **형식** 함수 개체를 변환할 수 있습니다.

`left` 개체는는 `_Pm` 에서 멤버 함수를 호출 합니다.

## <a name="return-value"></a>반환 값

조정 가능한 단항 함수입니다.

## <a name="remarks"></a>설명

템플릿 클래스는 `_Pm`의 복사본을 저장합니다. 이는 전용 멤버 개체에서 **Type** 클래스의 멤버 함수에 대한 포인터여야 합니다. 또한 해당 멤버 함수 `operator()`를 ( **left**.* `_Pm`)( )을 반환하는 것으로 정의합니다.

## <a name="example"></a>예제

`mem_fun_ref_t`의 생성자는 일반적으로 직접 사용되지 않습니다. 도우미 함수 `mem_fun_ref`은 멤버 함수를 적용하는 데 사용됩니다. 멤버 함수 어댑터를 사용하는 방법에 대한 예제는 [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref)를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<functional>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
