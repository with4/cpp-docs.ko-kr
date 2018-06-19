---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e0fd249dd7591caaaf62a0b8a698085efedb1f25
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854537"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

`vector<bool>::reference`을 `bool`로 묵시적으로 변환합니다.

## <a name="syntax"></a>구문

```cpp
operator bool() const;
```

## <a name="return-value"></a>반환 값

[vector\<bool>](../standard-library/vector-bool-class.md) 개체의 요소 부울 값

## <a name="remarks"></a>설명

`vector<bool>` 개체는 이 연산자로 수정할 수 없습니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<vector>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[벡터\<bool >:: 클래스 참조](../standard-library/vector-bool-reference-class.md)<br/>
[C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)<br/>
