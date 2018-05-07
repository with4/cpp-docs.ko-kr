---
title: 컴파일러 경고 (수준 4) C4709 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4709
dev_langs:
- C++
helpviewer_keywords:
- C4709
ms.assetid: 8abfdd45-8c70-4c27-b0fb-ca0c3f0fccf9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aab1727ab667a4434805f969b32957e654814166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4709"></a>컴파일러 경고(수준 4) C4709
배열 인덱스 식 내에 쉼표 연산자  
  
 쉼표에 배열 인덱스 식에서 발생 하는 경우 컴파일러는 마지막 쉼표 후 값을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4709 오류가 생성 됩니다.  
  
```  
// C4709.cpp  
// compile with: /W4  
#include <stdio.h>  
  
int main()   
{  
    int arr[2][2];  
    arr[0][0] = 10;  
    arr[0][1] = 11;  
  
    // Prints 10, not 11  
    printf_s("\n%d",arr[0][1,0]);   // C4709  
}  
```