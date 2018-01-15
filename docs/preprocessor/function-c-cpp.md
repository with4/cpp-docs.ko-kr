---
title: "함수 (C/c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- function_CPP
- vc-pragma.function
dev_langs: C++
helpviewer_keywords:
- function pragma
- pragmas, function
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ff72fb22adf3b81e936e3591f2a60b2aa2e30fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="function-cc"></a>함수 (C/C++)
pragma의 인수 목록에서 지정된 함수에 대한 호출이 생성되도록 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## <a name="remarks"></a>설명  
 사용 하는 경우는 **내장** pragma (또는 /Oi) 내장 함수 (내장 함수는 함수 호출 아니라 인라인 코드로 생성 됨)를 생성 하도록 컴파일러에 게 사용할 수 있습니다는 **함수** pragma 함수 호출을 명시적으로 강제로 합니다. function pragma가 표시되면 지정된 내장 함수를 포함하는 첫 번째 함수 정의에서 적용되며, 모양에 또는 소스 파일의 끝까지 계속 적용은 **내장** pragma는 동일한 내장 함수를 지정 합니다. **함수** pragma는 함수의 외부 에서만 사용할 수 등의 전역 수준에서 합니다.  
  
 내장 형식을 있는 함수 목록에 대 한 참조 [내장 #pragma](../preprocessor/intrinsic.md)합니다.  
  
## <a name="example"></a>예  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
```Output  
str is 'Now************'  
str is '!!!!!!!!!!!!!!!'  
```  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)