---
title: 컴파일러 오류 C2148 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2148
dev_langs:
- C++
helpviewer_keywords:
- C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f64f11f94c5a0c5d223d97b6b597f89b89aa160b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170702"
---
# <a name="compiler-error-c2148"></a>컴파일러 오류 C2148
0x7fffffff 바이트 배열의 전체 크기를 초과할 수 없습니다.  
  
 배열에는 제한을 초과합니다. 배열의 크기를 줄입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2148 오류가 생성 됩니다.  
  
```  
// C2148.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( ) {  
   char MyArray[0x7ffffffff];   // C2148  
   char * MyArray2 = (char *)malloc(0x7fffffff);  
  
   if (MyArray2)  
      printf_s("It worked!");  
   else  
      printf_s("It didn't work.");  
}  
```