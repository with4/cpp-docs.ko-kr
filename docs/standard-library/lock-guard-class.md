---
title: lock_guard 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dcbd0f17392c69b09d6f9f3c8123dfcf8b543fa4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="lockguard-class"></a>lock_guard 클래스

소멸자가 `mutex`의 잠금을 해제하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>설명

템플릿 인수 `Mutex`는 *뮤텍스 형식*의 이름을 지정해야 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 Typedefs

|이름|설명|
|----------|-----------------|
|`lock_guard::mutex_type`|템플릿 인수 `Mutex`에 대한 동의어입니다.|

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[lock_guard](#lock_guard)|`lock_guard` 개체를 생성합니다.|
|[lock_guard::~lock_guard 소멸자](#dtorlock_guard_destructor)|생성자에 전달된 `mutex`를 잠금 해제합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<뮤텍스 >

**네임스페이스:** std

## <a name="lock_guard"></a>  lock_guard::lock_guard 생성자

`lock_guard` 개체를 생성합니다.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>매개 변수

`Mtx` A *뮤텍스 형식* 개체입니다.

### <a name="remarks"></a>설명

첫 번째 생성자는 `lock_guard` 형식의 개체를 생성하고 `Mtx`를 잠급니다. `Mtx`가 재귀 뮤텍스가 아니면 이 생성자를 호출할 때 잠금이 해제되어 있어야 합니다.

두 번째 생성자는 `Mtx`를 잠그지 않습니다. 이 생성자를 호출할 때 `Mtx`가 잠겨 있어야 합니다. 생성자는 예외를 throw하지 않습니다.

## <a name="dtorlock_guard_destructor"></a>  lock_guard::~lock_guard 소멸자

생성자에 전달된 `mutex`를 잠금 해제합니다.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>설명

소멸자가 실행될 때 `mutex`가 없으면 동작이 정의되지 않습니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
