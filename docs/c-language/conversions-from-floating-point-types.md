---
title: 부동 소수점 형식에서 변환 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce86a9ceffaa5d9dacfe56e6b89b677b3abb1517
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="conversions-from-floating-point-types"></a>부동 소수점 형식에서 변환

**double**이나 **long double**로 변환된 **float** 값 또는 **long double**로 변환된 **double** 값은 변경되지 않습니다. **float** 값으로 변환된 **double** 값은 가능할 경우 정확하게 표현됩니다. 값을 정확하게 표현할 수 없는 경우 정밀도가 손실될 수 있습니다. 결과가 범위를 벗어나면 동작이 정의되지 않습니다. 부동 소수점 형식의 범위에 대해서는 [부동 소수점 상수에 대한 제한](../c-language/limits-on-floating-point-constants.md)을 참조하세요.

부동 소수점 값은 먼저 **long**으로 변환된 후 **long** 값에서 특정 정수 값으로 변환하여 정수 값으로 변환됩니다. **long**으로 변환할 때 부동 소수점 값의 소수 부분이 삭제됩니다. 결과가 커서 **long**에 맞지 않을 경우 변환 결과가 정의되지 않습니다.

**Microsoft 전용**

**double** 또는 **long double** 부동 소수점 숫자를 작은 부동 소수점 숫자로 변환할 때 언더플로가 발생하면 부동 소수점 변수의 값이 0으로 잘립니다. 오버플로가 발생하면 런타임 오류가 생성됩니다. Microsoft C 컴파일러가 **long double**을 **double** 형식으로 매핑합니다.

**Microsoft 전용 종료**

다음 표에서는 부동 형식의 변환을 요약합니다.

## <a name="conversions-from-floating-point-types"></a>부동 소수점 형식에서 변환

|시작|대상|메서드|
|----------|--------|------------|
|**float**|**char**|**long**으로 변환, **long**을 **char**로 변환|
|**float**|**short**|**long**으로 변환, **long**을 **short**로 변환|
|**float**|**long**|소수점에서 자릅니다. 결과가 커서 **long**으로 나타낼 수 없는 경우 결과가 정의되지 않습니다.|
|**float**|**unsigned short**|**long**으로 변환, **long**을 **unsigned short**로 변환|
|**float**|**unsigned long**|**long**으로 변환, **long**을 **unsigned long**으로 변환|
|**float**|**double**|내부 표현 변경|
|**float**|**long double**|내부 표현 변경|
|**double**|**char**|**float**로 변환, **float**를 **char**로 변환|
|**double**|**short**|**float**로 변환, **float**를 **short**로 변환|
|**double**|**long**|소수점에서 자릅니다. 결과가 커서 **long**으로 나타낼 수 없는 경우 결과가 정의되지 않습니다.|
|**double**|**unsigned short**|**long**으로 변환, **long**을 **unsigned short**로 변환|
|**double**|**unsigned long**|**long**으로 변환, **long**을 **unsigned long**으로 변환|
|**double**|**float**|**float**로 나타냅니다. **double** 값을 **float**로 정확히 나타낼 수 없으면 정밀도가 손실됩니다. 갓이 커서 **float**로 나타낼 수 없으면 결과가 정의되지 않습니다.|
|**long double**|**char**|**float**로 변환, **float**를 **char**로 변환|
|**long double**|**short**|**float**로 변환, **float**를 **short**로 변환|
|**long double**|**long**|소수점에서 자릅니다. 결과가 커서 **long**으로 나타낼 수 없는 경우 결과가 정의되지 않습니다.|
|**long double**|**unsigned short**|**long**으로 변환, **long**을 **unsigned short**로 변환|
|**long double**|**unsigned long**|**long**으로 변환, **long**을 **unsigned long**으로 변환|
|**long double**|**float**|**float**로 나타냅니다. **double** 값을 **float**로 정확히 나타낼 수 없으면 정밀도가 손실됩니다. 갓이 커서 **float**로 나타낼 수 없으면 결과가 정의되지 않습니다.|
|**long double**|**double**|**long double** 값은 **double**로 처리됩니다.|

변환되는 값이 최대 양수 **long** 값보다 클 경우 **float**, **double** 또는 **long double** 값에서 **unsigned long**으로 변환하는 것은 적절하지 않습니다.

## <a name="see-also"></a>참고 항목

[할당 변환](../c-language/assignment-conversions.md)  
