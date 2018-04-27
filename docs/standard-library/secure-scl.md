---
title: _SECURE_SCL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b75342fb28d31c9249657080c0abf10d0e99391b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="securescl"></a>_SECURE_SCL

[확인된 반복기](../standard-library/checked-iterators.md)가 사용하도록 설정되었는지를 정의하는 이 매크로는 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체되었습니다. 확인된 반복기는 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다.

> [!IMPORTANT]
> `_SECURE_SCL` 매크로는 더 이상 직접 사용할 수는 없습니다. 대신 `_ITERATOR_DEBUG_LEVEL`을 사용하여 확인된 반복기 설정을 제어합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

확인된 반복기를 사용하는 경우에는 안전하지 않은 반복기 사용으로 인해 런타임 오류가 발생하며 프로그램이 종료됩니다. 확인된 반복기를 사용하도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 1 또는 2로 설정합니다. 이 값은 `_SECURE_SCL` 설정 1(사용)과 동일합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

확인된 반복기를 사용하지 않도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 0으로 설정합니다. 이 값은 `_SECURE_SCL` 설정 0(사용 안 함)과 동일합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
