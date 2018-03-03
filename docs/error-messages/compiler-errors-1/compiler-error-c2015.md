---
title: "컴파일러 오류 C2015 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a04a5c113ca39dac137f2f225a8dcad9318a29bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2015"></a>컴파일러 오류 C2015
상수에 문자가 너무 많습니다.  
  
 문자 상수 두 개 이상의 문자를 포함 합니다. 표준 문자 상수에 대 한 하나의 문자 및 긴 문자 상수에 대 한 두 개의 문자도 제한이 됩니다.  
  
 예: \t 이스케이프 시퀀스를 하나의 문자로 변환 됩니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2015 오류가 생성 됩니다.  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## <a name="example"></a>예  
 C2015는 Microsoft 확장을 정수로 변환할 문자 상수를 사용 하는 경우에 발생할 수 있습니다.  다음 샘플에서는 C2015 오류가 생성 됩니다.  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```