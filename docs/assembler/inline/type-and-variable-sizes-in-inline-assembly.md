---
title: 형식 및 인라인 어셈블리에서 다양 한 크기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- length
- Type
dev_langs:
- C++
helpviewer_keywords:
- variables, length
- size, getting in inline assembly
- size
- LENGTH operator
- TYPE operator
- SIZE operator
- inline assembly, operators
- variables, type
- variables, size
ms.assetid: b62c2f2b-a7ad-4145-bae4-d890db86d348
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3466158c507e618e701df5aed35db7e5814abe52
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="type-and-variable-sizes-in-inline-assembly"></a>인라인 어셈블리의 형식 및 다양한 크기
**Microsoft 전용**  
  
 **길이**, **크기**, 및 **형식** 연산자는 인라인 어셈블리에서 제한 된 의미 합니다. MASM 지시문이나 연산자를 사용하여 데이터를 정의할 수 없으므로 이러한 연산자를 `DUP` 연산자와 함께 사용할 수는 없습니다. 그러나 C 또는 C++ 변수나 형식의 크기를 찾기 위해 사용할 수는 있습니다.  
  
-   **길이** 연산자 배열의 요소 수를 반환할 수 있습니다. 배열이 아닌 변수에 대해 값 1을 반환합니다.  
  
-   **크기** 연산자는 C 또는 c + + 변수의 크기를 반환할 수 있습니다. 변수의 크기는 제품의 해당 **길이** 및 **형식**합니다.  
  
-   **형식** 연산자는 C 또는 c + + 형식 또는 변수의 크기를 반환할 수 있습니다. 변수는 배열 이면 **형식** 배열의 단일 요소 크기를 반환 합니다.  
  
 예를 들어, 프로그램에 요소가 8개인 `int` 배열이 있을 경우  
  
```  
int arr[8];  
```  
  
 다음 C 및 어셈블리 식에서 `arr`과 그 요소의 크기를 구합니다.  
  
|__asm|C|크기|  
|-------------|-------|----------|  
|**길이** arr|`sizeof`(arr)/`sizeof`(arr[0])|8|  
|**크기** arr|`sizeof`(arr)|32|  
|**형식** arr|`sizeof`(arr[0])|4|  
  
 **Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [__asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)