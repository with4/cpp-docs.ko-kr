---
title: vector&lt;bool&gt;::reference::operator bool | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89a027f9c31b9779991ebaee80b4e9d1a97d8ff7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
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
