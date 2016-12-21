---
title: "#define 지시문 (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#define"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#define 지시문"
  - "#define 지시문, 구문"
  - "define 지시문(#define)"
  - "define 지시문(#define), 구문"
  - "전처리기, 지시문"
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #define 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define`은 식별자 또는 매개 변수화된 식별자와 토큰 문자열을 연계한 *매크로*를 생성합니다.  매크로가 정의된 후 컴파일러는 소스 파일에서 발생하는 각 식별자를 토큰 문자열로 대체할 수 있습니다.  
  
## 구문  
 `#define` *identifier* *token\-string*opt  
  
 `#define` *identifier*`(` *identifier*opt`,` *...* `,` *identifier*opt `)` *token\-string*opt  
  
## 설명  
 `#define` 지시문은 컴파일러가 소스 파일에서 발생하는 각 *identifier*를 *token\-string*으로 대체하도록 합니다.  *identifier*는 토큰을 만들 경우에만 대체됩니다.  다시 말해 *identifier*는 주석, 문자열 또는 긴 식별자의 일부로 표시되는 경우 대체되지 않습니다.  자세한 내용은 [C\+\+ 토큰](../cpp/tokens-cpp.md)을 참조하십시오.  
  
 *token\-string* 인수는 키워드, 상수 또는 완전한 문과 같은 일련의 토큰으로 구성됩니다.  하나 이상의 공백 문자로 *token\-string*을 *identifier*와 구분해야 합니다.  이 공백은 대체 텍스트의 일부 또는 대체 텍스트의 최종 토큰 뒤에 오는 공백으로 간주되지 않습니다.  
  
 *token\-string*이 없는 `#define`은 소스 파일에서 *identifier*가 발생하지 않도록 합니다.  *identifier*는 정의된 상태를 유지하며 `#if defined` 및 `#ifdef` 지시문을 사용하여 테스트할 수 있습니다.  
  
 두 번째 구문 형식에서는 매개 변수를 사용하여 함수 형식 매크로를 정의합니다.  이 형식은 괄호 안에 표시되어야 하는 매개 변수의 선택 목록을 허용합니다.  매크로가 정의된 후에 발생하는 각 *identifier*\(*identifier*opt, ..., *identifier*opt\)는 형식 매개 변수를 대체하는 실제 인수를 가진 *token\-string* 인수 형태로 교체됩니다.  
  
 대체 실제 값의 위치를 표시하기 위해 형식 매개 변수 이름은 *token\-string*에 나타납니다.  각 매개 변수 이름은 *token\-string*에 여러 번 표시될 수 있으며 이름은 순서에 관계없이 표시할 수 있습니다.  호출의 인수 개수는 매크로 정의의 매개 변수 개수와 일치해야 합니다.  괄호를 자유롭게 사용하여 복잡한 실제 인수가 올바르게 해석되도록 합니다.  
  
 목록의 형식 매개 변수는 쉼표로 구분됩니다.  목록의 각 이름은 고유해야 하고 목록은 괄호로 묶여야 합니다.  *identifier* 및 여는 괄호를 띄어쓰기로 분리할 수 없습니다.  newline 문자 바로 앞에 백슬래시\(`\`\)를 배치하여 여러 소스 줄로 된 긴 지시문에 줄 연결을 사용합니다.  형식 매개 변수 이름의 범위는 *token\-string*으로 끝나는 새 줄로 확장됩니다.  
  
 매크로가 두 번째 구문 형식으로 정의된 경우, 인수 목록이 그 뒤에 오는 텍스트 인스턴스는 매크로 호출을 나타냅니다.  소스 파일의 *identifier* 인스턴스 뒤에 오는 실제 인수는 매크로 정의에서 그에 대응하는 형식 매개 변수와 일치합니다.  stringizing\(`#`\), charizing \(`#@`\) 또는 token\-pasting\(`##`\) 연산자가 앞에 붙지 않거나 `##` 연산자가 뒤따르지 않는 *token\-string*의 각 형식 매개 변수는 그에 대응하는 실제 인수로 대체됩니다.  실제 인수의 모든 매크로는 지시문이 형식 매개 변수를 대체하기 전에 확장됩니다. 연산자는 [전처리기 연산자](../preprocessor/preprocessor-operators.md)에 설명되어 있습니다.  
  
 인수를 가진 매크로에 대한 다음 예제는 `#define` 구문의 두 번째 형식을 설명합니다.  
  
```  
// Macro to define cursor lines   
#define CURSOR(top, bottom) (((top) << 8) | (bottom))  
  
// Macro to get a random integer with a specified range   
#define getrandom(min, max) \  
    ((rand()%(int)(((max) + 1)-(min)))+ (min))  
```  
  
 파생 효과가 있는 인수를 사용하면 매크로가 예기치 않은 결과를 생성하기도 합니다.  주어진 형식 매개 변수는 *token\-string*에서 두 번 이상 나타날 수 있습니다.  해당 형식 매개 변수가 파생 효과가 있는 식으로 대체되는 경우 해당 식은 그 파생 효과로 인해 두 번 이상 계산됩니다. [토큰 붙여넣기 연산자\(\#\#\)](../preprocessor/token-pasting-operator-hash-hash.md) 아래의 예제를 참조하십시오.  
  
 `#undef` 지시문으로 인해 식별자의 전처리기 정의가 무시될 수 있습니다.  자세한 내용은 [\#undef 지시문](../preprocessor/hash-undef-directive-c-cpp.md)을 참조하십시오.  
  
 정의된 매크로의 이름이 *token\-string*에서 발생하는 경우\(다른 매크로 확장의 결과로 발생하는 경우도 해당\) 매크로가 확장되지 않습니다.  
  
 같은 이름을 가진 매크로에 대한 두 번째 `#define`은 두 번째 토큰 시퀀스가 첫 번째와 동일하지 않으면 경고를 생성합니다.  
  
 **Microsoft 전용**  
  
 Microsoft C\/C\+\+에서는 새 정의가 원래 정의와 구문적으로 동일할 경우 매크로를 재정의할 수 있습니다.  즉, 두 개의 정의에서 매개 변수 이름은 각기 다를 수 있습니다.  이 동작은 두 정의의 어휘가 동일해야 하는 [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C와는 다릅니다.  
  
 예를 들어, 다음 두 매크로는 매개 변수 이름만 제외하면 모두 동일합니다.  [!INCLUDE[vcpransi](../preprocessor/includes/vcpransi_md.md)] C는 재정의를 허용하지 않지만 Microsoft C\/C\+\+는 오류 없이 컴파일합니다.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( a1 * a2 )  
```  
  
 한편 다음 동일하지 않은 두 매크로는 Microsoft C\/C\+\+에서 경고를 생성합니다.  
  
```  
#define multiply( f1, f2 ) ( f1 * f2 )  
#define multiply( a1, a2 ) ( b1 * b2 )  
```  
  
 **Microsoft 전용 종료**  
  
 이 예제에서는 `#define` 지시문을 설명합니다.  
  
```  
#define WIDTH       80  
#define LENGTH      ( WIDTH + 10 )  
```  
  
 첫 번째 명령문은 `WIDTH` 식별자를 정수 상수 80으로 정의하고, `LENGTH`를 `WIDTH` 더하기 정수 상수 10으로 정의합니다.  `LENGTH`가 나타날 때마다 \(`WIDTH + 10`\)으로 바뀝니다.  또한, `WIDTH + 10`이 발생할 때마다 \(`80 + 10`\) 식으로 바뀝니다.  `WIDTH + 10`을 묶는 괄호는 다음과 같은 문에서 해석을 제어하기 때문에 중요합니다.  
  
```  
var = LENGTH * 20;  
```  
  
 전처리 단계 후 문은 다음과 같아집니다.  
  
```  
var = ( 80 + 10 ) * 20;  
```  
  
 결과 값이 1800으로 계산됩니다.  괄호가 없을 경우 결과는 다음과 같습니다.  
  
```  
var = 80 + 10 * 20;  
```  
  
 결과 값이 280으로 계산됩니다.  
  
 **Microsoft 전용**  
  
 [\/D](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용하여 매크로 및 상수를 정의하면 파일 시작 부분에 `#define` 전처리 지시문을 사용하는 것과 같은 효과가 나타납니다.  \/D 옵션을 사용하여 최대 30 매크로로 정의할 수 있습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)