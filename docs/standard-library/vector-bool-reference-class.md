---
title: vector&lt;bool&gt;::reference 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- vector/vector<bool>::reference
dev_langs:
- C++
helpviewer_keywords:
- vector<bool> reference class
ms.assetid: f27854f9-0ef0-4e7e-ad2e-cd53b6cb3334
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 149b43f0485d3717ad2f413d2519e435f0da0562
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857079"
---
# <a name="vectorltboolgtreference-class"></a>vector&lt;bool&gt;::reference 클래스

`vector<bool>::reference` 클래스는 [vector\<bool> 클래스](../standard-library/vector-bool-class.md)에서 `bool&`을 시뮬레이션하도록 제공되는 프록시 클래스입니다.

## <a name="remarks"></a>설명

C++는 기본적으로 비트에 직접 참조를 허용하지 않으므로 시뮬레이션된 참조가 필요하지 않습니다. `vector<bool>`는 요소당 1비트만 사용하며, 이 프록시 클래스만 사용하여 참조할 수 있습니다. 하지만, 특정 할당은 유효하지 않으므로 참조 시뮬레이션이 완전하지 않습니다. 예를 들어 `vector<bool>::reference` 개체의 주소를 확인할 수 없으므로 [vector\<bool>::operator&#91;&#93;](http://msdn.microsoft.com/Library/97738633-690d-4069-b2d9-8c54104fbfdd)를 사용하는 다음 코드는 올바르지 않습니다.

```cpp
vector<bool> vb;
// ...
bool* pb = &vb[1]; // conversion error - do not use
bool& refb = vb[1];   // conversion error - do not use
```

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[flip](../standard-library/vector-bool-reference-flip.md)|벡터 요소의 부울 값을 반전합니다.|
|[operator bool](../standard-library/vector-bool-reference-operator-bool.md)|`vector<bool>::reference`을 `bool`로 묵시적으로 변환합니다.|
|[operator=](../standard-library/vector-bool-reference-operator-assign.md)|비트에 부울 값을 할당하거나 참조된 요소에 저장된 값을 비트에 할당합니다.|

## <a name="requirements"></a>요구 사항

**헤더**: \<vector>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<vector>](../standard-library/vector.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
