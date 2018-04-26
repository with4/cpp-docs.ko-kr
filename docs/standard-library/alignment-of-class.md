---
title: alignment_of 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9af19f046cf6de44448e3fcddf97584f58adc9ae
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="alignmentof-class"></a>alignment_of 클래스

지정된 형식의 맞춤을 가져옵니다. 이 구조체는 [alignof](../cpp/alignof-and-alignas-cpp.md) 측면에서 구현됩니다. 맞춤 값을 쿼리만 하면 되는 경우 `alignof`를 직접 사용합니다. 태그 디스패치를 수행하는 경우처럼 정수 계열 상수가 필요한 경우 alignment_of를 사용합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>매개 변수

`Ty` 형식이 쿼리입니다.

## <a name="remarks"></a>설명

형식 쿼리는 `Ty` 형식의 맞춤 값을 보유합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<type_traits>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage 클래스](../standard-library/aligned-storage-class.md)<br/>
