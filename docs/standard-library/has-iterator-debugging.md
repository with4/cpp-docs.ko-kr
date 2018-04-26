---
title: _HAS_ITERATOR_DEBUGGING | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6cf83c0877c351a2bf247a557f3df53e9c1f22
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체된 이 매크로는 반복기 디버깅 기능이 디버그 빌드에서 사용하도록 설정되었는지 여부를 정의합니다. 반복기 디버깅은 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다. 자세한 내용은 [디버그 반복기 지원](../standard-library/debug-iterator-support.md)을 참조하세요.

> [!IMPORTANT]
> `_HAS_ITERATOR_DEBUGGING` 매크로는 직접 사용되지 않습니다. 대신 `_ITERATOR_DEBUG_LEVEL`을 사용하여 반복기 디버그 설정을 제어합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

디버그 빌드에서 반복기 디버깅을 사용하도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 2로 설정합니다. 이 값은 `_HAS_ITERATOR_DEBUGGING` 설정 1(사용)과 동일합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

일반 정품 빌드에서는 `_ITERATOR_DEBUG_LEVEL`을 2로 설정할 수 없고 `_HAS_ITERATOR_DEBUGGING`을 1로 설정할 수 없습니다.

디버그 빌드에서 디버그 반복기를 사용하지 않도록 설정하려면 `_ITERATOR_DEBUG_LEVEL`을 0 또는 1로 설정합니다. 이 값은 `_HAS_ITERATOR_DEBUGGING` 설정 0(사용 안 함)과 동일합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
