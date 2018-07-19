---
title: _SECURE_SCL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SECURE_SCL
dev_langs:
- C++
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6a9fa05a4cb8c421a511a30fd62310d69003fde
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966435"
---
# <a name="securescl"></a>_SECURE_SCL

[확인된 반복기](../standard-library/checked-iterators.md)가 사용하도록 설정되었는지를 정의하는 이 매크로는 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)로 교체되었습니다. 확인된 반복기는 기본적으로 디버그 빌드에서는 사용하도록 설정되고 정품 빌드에서는 사용하지 않도록 설정됩니다.

> [!IMPORTANT]
> _SECURE_SCL 매크로 직접 사용 하는 사용 되지 않습니다. 대신 컨트롤을 사용 하 여 _ITERATOR_DEBUG_LEVEL 반복기 설정을 확인합니다. 자세한 내용은 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)을 참조하세요.

## <a name="remarks"></a>설명

확인된 반복기를 사용하는 경우에는 안전하지 않은 반복기 사용으로 인해 런타임 오류가 발생하며 프로그램이 종료됩니다. 확인 된 반복기를 사용 하도록 설정 하려면 1 또는 2로 _ITERATOR_DEBUG_LEVEL을 설정 합니다. 이 1 _SECURE_SCL 설정을 동일 또는 사용 하도록 설정 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

확인 된 반복기를 사용 하지 않으려면 _ITERATOR_DEBUG_LEVEL 0으로 설정 합니다. 이 0 _SECURE_SCL 설정을 동일 또는 사용 하지 않도록 설정 합니다.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

확인된 반복기에 대한 경고를 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
