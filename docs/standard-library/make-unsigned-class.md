---
title: make_unsigned 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aba0421ab55d5cf30b38f69e58123fbd4056d16f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="makeunsigned-class"></a>make_unsigned 클래스

형식을 만들거나 형식의 크기보다 크거나 같은 부호가 없는 가장 작은 형식을 만듭니다.

## <a name="syntax"></a>구문

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`T`|수정할 형식입니다.|

## <a name="remarks"></a>설명

형식 한정자의 인스턴스는 `is_unsigned<T>`가 true일 때 `T`인 수정된 형식을 가집니다. 그렇지 않은 경우 가장 작은 부호 있는 형식 `ST`이며, 여기서 `sizeof (T) <= sizeof (ST)`입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
