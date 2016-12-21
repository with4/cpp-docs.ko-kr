---
title: "switch 문 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default"
  - "default_cpp"
  - "switch"
  - "switch_cpp"
  - "case"
  - "case_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case 키워드[C++], switch 문에서"
  - "default 키워드[C++]"
  - "switch 키워드[C++]"
ms.assetid: 6c3f3ed3-5593-463c-8f4b-b33742b455c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# switch 문 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정수 계열 식의 값에 따라 코드의 여러 섹션 중에서 선택할 수 있습니다.  
  
## 구문  
  
```  
  
      switch ( expression )  
   case constant-expression : statement  
   [default  : statement]  
```  
  
## 설명  
 *expression*은 정수 계열 형식 또는 정수 계열 형식으로의 명확한 변환이 있는 클래스 형식이어야 합니다.  정수 계열 확장은 [정수 계열 확장](../misc/integral-promotions.md)에 설명된 대로 수행됩니다.  
  
 `switch` 문 본문은 일련의 **case** 레이블과 선택적 **default** 레이블로 구성됩니다.  **case** 문에서는 어떤 두 상수 식도 동일한 값으로 계산될 수 없습니다.  **default** 레이블은 한 번만 나타날 수 있습니다.  레이블 문은 구문적 요구 사항이 아니지만 `switch` 문은 레이블 문이 없으면 의미가 없습니다.   기본 문은 끝에 오지 않아도 되며 switch 문의 본문 중 어느 위치에나 나타날 수 있습니다.  case 또는 default 레이블은 switch 문 내에만 나타날 수 있습니다.  
  
 각 **case** 레이블의 *constant\-expression*은 *expression*의 형식으로 변환되고 *expression*과 같은지 비교됩니다.  **case** *constant\-expression*이 *expression*의 값과 일치하는 문으로 제어가 전달됩니다.  결과적으로 발생하는 동작은 다음 표에 나와 있습니다.  
  
### switch 문 동작  
  
|조건|작업|  
|--------|--------|  
|변환된 값이 승격된 제어 식의 값과 일치합니다.|제어가 해당 레이블 뒤에 오는 문으로 전송됩니다.|  
|어떤 상수도 **case** 레이블의 상수와 일치하지 않고 **default** 레이블이 있습니다.|제어가 **default** 레이블로 전송됩니다.|  
|어떤 상수도 **case** 레이블의 상수와 일치하지 않고 **default** 레이블이 없습니다.|제어가 `switch` 문 뒤의 문으로 전송됩니다.|  
  
 일치하는 식이 발견되면 후속 **case** 또는 **default** 레이블에 의해 제어가 방해되지 않습니다.  실행을 중지하고 `switch` 문 뒤의 문으로 제어를 전송하는 데에는 [break](../cpp/break-statement-cpp.md) 문이 사용됩니다.  **break** 문이 없으면 일치하는 **case** 레이블에서 `switch`의 끝까지\(**default** 포함\) 모든 문이 실행됩니다.  예를 들면 다음과 같습니다.  
  
```  
// switch_statement1.cpp  
#include <stdio.h>  
  
int main() {  
   char *buffer = "Any character stream";  
   int capa, lettera, nota;  
   char c;  
   capa = lettera = nota = 0;  
  
   while ( c = *buffer++ )   // Walks buffer until NULL  
   {  
      switch ( c )  
      {  
         case 'A':  
            capa++;  
            break;  
         case 'a':  
            lettera++;  
            break;  
         default:  
            nota++;  
      }  
   }  
   printf_s( "\nUppercase a: %d\nLowercase a: %d\nTotal: %d\n",  
      capa, lettera, (capa + lettera + nota) );  
}  
```  
  
 위의 예제에서 `capa`는 `c`가 대문자 `A`인 경우 증가됩니다.  `capa++` 뒤의 `break` 문이 `switch` 문 본문의 실행을 종료하고 제어를 `while` 루프로 전달합니다.  `break` 문이 없으면 `lettera` 및 `nota`도 증가됩니다.  `case 'a'`에 대한 `break` 문도 비슷한 역할을 합니다.  `c`가 소문자 `a`인 경우 `lettera`가 증가하고 `break` 문이 `switch` 문 본문을 종료합니다.  `c`가 `a` 또는 `A`가 아닌 경우 `default` 문이 실행됩니다.  
  
 `switch` 문의 내부 블록은 도달할 수 있는 한, 즉 가능한 모든 실행 경로에 의해 건너뛰어지지 않는 한 초기화를 사용하는 정의를 포함할 수 있습니다.  이러한 선언을 사용하여 정의된 이름에는 로컬 범위가 있습니다.  예를 들면 다음과 같습니다.  
  
```  
// switch_statement2.cpp  
// C2360 expected  
#include <iostream>  
using namespace std;  
int main(int argc, char *argv[])  
{  
   switch( tolower( *argv[1] ) )  
   {  
       // Error. Unreachable declaration.  
       char szChEntered[] = "Character entered was: ";  
  
   case 'a' :  
       {  
       // Declaration of szChEntered OK. Local scope.  
       char szChEntered[] = "Character entered was: ";  
       cout << szChEntered << "a\n";  
       }  
       break;  
  
   case 'b' :  
       // Value of szChEntered undefined.  
       cout << szChEntered << "b\n";  
       break;  
  
   default:  
       // Value of szChEntered undefined.  
       cout << szChEntered << "neither a nor b\n";  
       break;  
   }  
}  
```  
  
 `switch` 문은 중첩될 수 있습니다.  이러한 경우 **case** 또는 **default** 레이블은 가장 가까운 바깥쪽 `switch` 문에 연결됩니다.  
  
## Microsoft 전용  
 Microsoft C는 `switch` 문의 case 값 수를 제한하지 않습니다.  이 수는 사용 가능한 메모리에 의해서만 제한됩니다.  ANSI C의 경우 `switch` 문에서 257개 이상의 case 레이블이 허용되어야 합니다.  
  
 기본적으로 Microsoft C에는 Microsoft 확장을 사용하도록 설정되어 있습니다.  [\/Za](../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 사용하여 이러한 확장을 비활성화하십시오.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [선택문](../cpp/selection-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) Using Labels in the case Statement](http://msdn.microsoft.com/ko-kr/a6ff057d-1aee-42ed-a28d-ee6a565b3197)