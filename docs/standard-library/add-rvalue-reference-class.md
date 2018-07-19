---
title: add_rvalue_reference 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba90002bc16dee6def7f8de69314668204ff5466
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966623"
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference 클래스

개체 또는 함수 형식인 경우 템플릿 매개 변수의 rvalue 참조 형식을 만듭니다. 아닌 경우, 참조 축소에 대한 의미 체계 때문에 형식이 템플릿 매개 변수와 동일합니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>매개 변수

*T* 수정할 형식입니다.

## <a name="remarks"></a>설명

합니다 `add_rvalue_reference` 클래스에 명명 된 멤버가 `type`를 템플릿 매개 변수를 rvalue 참조 형식의 별칭인 *T*합니다. 참조 축소의 의미 체계는 비 개체 및 비 함수 형식에 대 한 의미 *T*를 `T&&` 되는 *T*합니다. 예를 들어 *T* lvalue 참조 형식으로 `add_rvalue_reference<T>::type` 는 lvalue 참조 형식 rvalue 참조가 아닙니다.

편의 위해 \<type_traits > 도우미 템플릿으로 정의 `add_rvalue_reference_t`, 해당 별칭을 `type` 소속 `add_rvalue_reference`합니다.

## <a name="example"></a>예

static_assert를 사용하는 이 코드 예제에서는 `add_rvalue_reference` 및 `add_rvalue_reference_t`를 사용하여 rvalue 참조 형식을 만드는 방법과 lvalue 참조 형식에 대한 `add_rvalue_reference`의 결과가 rvalue 참조가 아닌 lvalue 참조 형식으로 축소되는 방법을 보여 줍니다.

```cpp
// ex_add_rvalue_reference.cpp
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp
#include <type_traits>
#include <iostream>
#include <string>

using namespace std;
int main()
{
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,
        "Expected add_rvalue_reference_t<string> to be string&&");
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,
        "Expected add_rvalue_reference_t<string*> to be string*&&");
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,
        "Expected add_rvalue_reference_t<string&> to be string&");
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,
        "Expected add_rvalue_reference_t<string&&> to be string&&");
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;
    return 0;
}

/*Output:
All static_assert tests of add_rvalue_reference passed.
*/
```

## <a name="requirements"></a>요구 사항

헤더: <type_traits> 네임스페이스: std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_lvalue_reference 클래스](../standard-library/add-lvalue-reference-class.md)<br/>
[is_rvalue_reference 클래스](../standard-library/is-rvalue-reference-class.md)<br/>
