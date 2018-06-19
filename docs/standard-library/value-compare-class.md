---
title: value_compare 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- value_compare
dev_langs:
- C++
helpviewer_keywords:
- value_compare class
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 594f3aaa45638ff2ab5d184a771070d87dbeb0bb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856585"
---
# <a name="valuecompare-class"></a>value_compare 클래스

키 값 비교를 통해 hash_map의 요소를 비교하여 hash_map 내의 상대 순서를 확인할 수 있는 함수 개체를 제공합니다.

## <a name="syntax"></a>구문

```cpp
class value_compare
 : std::public binary_function<value_type, value_type, bool>
{
public:
    bool operator()(
    const value_type& left,
    const value_type& right) const
 {
    return (comp(left.first, right.first));

}
protected:
    value_compare(const key_compare& c) : comp (c) { }
    key_compare comp;
};
```

## <a name="remarks"></a>설명

hash_map에 포함된 전체 요소의 **value_types** 간에 value_compare가 제공하는 비교 기준은 보조 클래스 생성에 의한 개별 요소의 키 간 비교에서 제공됩니다. 구성원 함수 연산자는 value_compare에서 제공하는 함수 개체에 저장된 `key_compare` 형식의 개체 **comp**를 사용하여 두 요소의 정렬 키 구성 요소를 비교합니다.

키 값이 요소 값과 동일한 단순 컨테이너인 hash_sets 및 hash_multisets의 경우 value_compare는 `key_compare`와 동일합니다. 반면 hash_maps 및 hash_multimaps의 경우에는 `pair` 형식 요소의 값이 요소 키의 값과 동일하지 않으므로 value_compare가 key_compare와 동일하지 않습니다.

## <a name="example"></a>예제

value_compare를 선언하고 사용하는 방법의 예제는 [hash_map::value_comp](../standard-library/hash-map-class.md#value_comp)의 예제를 참조하세요.

## <a name="requirements"></a>요구 사항

**헤더:** \<hash_map>

**네임스페이스:** stdext

## <a name="see-also"></a>참고자료

[binary_function 구조체](../standard-library/binary-function-struct.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
