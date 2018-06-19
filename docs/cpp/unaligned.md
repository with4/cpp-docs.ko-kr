---
title: __unaligned | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __unaligned_cpp
dev_langs:
- C++
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d73b082b9f41d03eb0b1a8c9fe772351ff4da91f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420918"
---
# <a name="unaligned"></a>__unaligned

**Microsoft 전용**합니다. 포인터를 `__unaligned` 한정자로 선언하는 경우, 컴파일러는 포인터가 정렬되지 않은 데이터의 주소 지정한다고 가정합니다. 따라서 플랫폼에 적절 한 코드 정렬 되지 않은 읽기를 처리 하도록 생성 되 고 포인터를 통해 씁니다.

## <a name="remarks"></a>설명

이 한정자 설명 포인터가; 데이터 맞춤 포인터 자체는 정렬 된 것으로 간주 됩니다.

에 대 한 필요성은 `__unaligned` 키워드 플랫폼과 환경에 따라 다릅니다. 데이터를 적절 하 게 표시 하지 않으면 성능 저하가에서 하드웨어 오류에 이르는 다양 한 문제가 발생할 수 있습니다. `__unaligned` 한정자 x86 적합 하지 않습니다. 플랫폼입니다.

정렬에 대한 자세한 내용은 다음을 참조하십시오.

- [align](../cpp/align-cpp.md)

- [__alignof 연산자](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)

- [구조체 맞춤 예제](../build/examples-of-structure-alignment.md)

## <a name="see-also"></a>참고자료

[키워드](../cpp/keywords-cpp.md)
