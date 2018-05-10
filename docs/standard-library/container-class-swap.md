---
title: 컨테이너 Class::swap | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f0ac2b3322f7f034c09c86f2307da2e3f3995c0d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="container-classswap"></a>Container Class::swap

> [!NOTE]
> 이 항목은 C++ 표준 라이브러리에서 사용되는 작동하지 않는 컨테이너 예제로 Visual C++ 설명서에 포함되어 있습니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

**\*this**와 해당 인수 간에 제어되는 시퀀스를 교환합니다.

## <a name="syntax"></a>구문

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>설명

**\*this.get\_allocator ==** _right_**.get_allocator**인 경우 일정한 시간 내에 교환합니다. 그렇지 않으면 두 개의 제어되는 시퀀스에 있는 요소 수에 비례하여 많은 요소 할당 및 생성자 호출을 수행합니다.

## <a name="see-also"></a>참고자료

[샘플 컨테이너 클래스](../standard-library/sample-container-class.md)<br/>
