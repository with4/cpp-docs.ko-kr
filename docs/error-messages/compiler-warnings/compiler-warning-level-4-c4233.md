---
title: 컴파일러 경고 (수준 4) C4233 | Microsoft Docs
ms.custom: ''
ms.date: 10/25/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4233
dev_langs:
- C++
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a933d41fd8e7cf3b94e458efff72193b8ce5e187
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297838"
---
# <a name="compiler-warning-level-4-c4233"></a>컴파일러 경고(수준 4) C4233

> 비표준 확장이 사용 됨: '*키워드*' 키워드를 c + +에서는 C 아님만 지원

컴파일러는 c + +에서는 아닌 C로 소스 코드를 컴파일 및 c + +에만 유효 하는 키워드를 사용 합니다. 컴파일러는 소스 파일의 확장명은.c 또는 사용 하는 경우 C로 소스 파일을 컴파일합니다 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)합니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다. 예를 들어를 수준 4 경고로 c4233이 줄을 소스 코드 파일을 추가 합니다.

```cpp
#pragma warning(4:4233)
```
