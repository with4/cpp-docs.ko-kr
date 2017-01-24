---
title: "함수 (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "function_CPP"
  - "vc-pragma.function"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "함수 pragma"
  - "pragma, 함수"
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 함수 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

pragma의 인수 목록에서 지정된 함수에 대한 호출이 생성되도록 지정합니다.  
  
## 구문  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## 설명  
 **intrinsic** pragma\(또는 \/Oi\)를 사용하여 컴파일러에 내장 함수를 생성하도록 지시하는 경우\(내장 함수는 함수 호출이 아닌 인라인 코드로 생성됨\), **function** pragma를 사용하여 함수 호출을 명시적으로 실행할 수 있습니다.  function pragma가 표시되면 지정된 내장 함수를 포함하는 첫 번째 함수 정의에서 적용되며,  동일한 내장 함수를 지정하는 **intrinsic** pragma가 나타날 때까지나 소스 파일의 끝까지 효과가 지속됩니다.  **function** pragma는 함수의 외부에서만\(전역 수준에서\) 사용할 수 있습니다.  
  
 내장 형식을 사용하는 함수 목록을 보려면 [\#pragma intrinsic](../preprocessor/intrinsic.md)을 참조하십시오.  
  
## 예제  
  
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
  
  **str is 'Now\*\*\*\*\*\*\*\*\*\*\*\*'**  
**str is '\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!'**   
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)