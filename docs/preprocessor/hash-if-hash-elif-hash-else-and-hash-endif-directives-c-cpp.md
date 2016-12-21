---
title: "#if, #elif, #else, and #endif 지시문 (C/C++) | Microsoft Docs"
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
  - "#else"
  - "#endif"
  - "#if"
  - "#elif"
  - "Defined"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#elif 지시문"
  - "#else 지시문"
  - "#endif 지시문"
  - "#if 지시문"
  - "조건부 컴파일, 지시문"
  - "defined 지시문"
  - "elif 지시문(#elif)"
  - "else 지시문(#else)"
  - "endif 지시문(#endif)"
  - "if 지시문(#if)"
  - "전처리기, 지시문"
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #if, #elif, #else, and #endif 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#if` 지시문은 `#elif`, `#else` 및 `#endif` 지시문과 함께 소스 파일 부분들의 컴파일을 제어합니다.  `#if` 뒤에 작성하는 식에 0이 아닌 값이 있는 경우 `#if` 지시문 바로 다음에 나오는 줄 그룹은 변환 단위에서 유지됩니다.  
  
## 문법  
 *conditional* :  
 *if\-part elif\-parts* opt *else\-part*opt *endif\-line*  
  
 *if\-part* :  
 *if\-line text*  
  
 *if\-line* :  
 **\#if**  *constant\-expression*  
  
 **\#ifdef**  *identifier*  
  
 **\#ifndef**  *identifier*  
  
 *elif\-parts* :  
 *elif\-line text*  
  
 *elif\-parts elif\-line text*  
  
 *elif\-line* :  
 **\#elif**  *constant\-expression*  
  
 *else\-part* :  
 *else\-line text*  
  
 *else\-line* :  
 `#else`  
  
 *endif\-line* :  
 `#endif`  
  
 소스 파일의 각 `#if` 지시문은 닫는 `#endif` 지시문과 일치해야 합니다.  원하는 수의 `#elif` 지시문이 `#if` 및 `#endif` 지시문 사이에 나타날 수 있지만 `#else` 지시문은 하나만 허용됩니다.  `#else` 지시문\(있을 경우\)은 `#endif` 앞에 있는 마지막 지시문이어야 합니다.  
  
 `#if`, `#elif`, `#else` 및 `#endif` 지시문은 다른 `#if` 지시문의 텍스트 부분에서 중첩될 수 있습니다.  중첩된 각 `#else`, `#elif` 또는 `#endif` 지시문은 가장 가까운 이전 `#if` 지시문에 속합니다.  
  
 `#if` 및 **\#ifdef**와 같은 모든 조건부 컴파일 지시문은 파일이 끝나기 전에 닫는 `#endif` 지시문과 일치해야 합니다. 그렇지 않으면 오류 메시지가 생성됩니다.  조건부 컴파일 지시문이 포함 파일에 포함된 경우 동일한 조건을 만족해야 합니다. 포함 파일의 끝에 일치하지 않는 조건부 컴파일 지시문이 없어야 합니다.  
  
 매크로 대체는 `#elif` 명령 다음에 나오는 명령줄의 부분 안에서 수행되므로 *constant\-expression*에서 매크로 호출을 사용할 수 있습니다.  
  
 전처리기는 추가 처리를 위해 지정된 *text* 항목 중 하나를 선택합니다.  *text*에서 지정된 블록은 임의의 텍스트 시퀀스일 수 있으며  두 줄 이상을 차지할 수 있습니다.  일반적으로 *text*는 컴파일러 또는 전처리기에 의미가 있는 프로그램 텍스트입니다.  
  
 전처리기는 선택한 *text*를 처리하여 컴파일러에 전달합니다.  *text*에 전처리기 지시문이 포함된 경우 전처리기는 해당 지시문을 수행합니다.  전처리기에서 선택한 텍스트 블록만 컴파일됩니다.  
  
 전처리기는 0이 아닌\(true\) 상수 식을 찾을 때까지 각각의 `#if` 또는 `#elif` 지시문 뒤에 나오는 상수 식을 평가하여 단일 *text* 항목을 선택합니다.  전처리기는 관련 `#elif`, `#else` 또는 `#endif`까지 모든 텍스트\(**\#**으로 시작하는 다른 전처리기 지시문 포함\)를 선택합니다.  
  
 발생한 모든 *constant\-expression*이 false이거나 `#elif` 지시문이 나타나지 않는 경우 전처리기는 `#else` 절 다음의 텍스트 블록을 선택합니다.  `#else` 절이 생략되고 `#if` 블록의 *constant\-expression* 인스턴스가 모두 false인 경우 텍스트 블록이 선택되지 않습니다.  
  
 *constant\-expression*은 이러한 추가 제한이 있는 정수 상수 식입니다.  
  
-   식은 정수 계열 형식이어야 하며 정수 상수, 문자 상수 및 **defined** 연산자만 포함할 수 있습니다.  
  
-   식에서는 `sizeof` 또는 형식 캐스팅 연산자를 사용할 수 없습니다.  
  
-   대상 개발 환경은 모든 범위의 정수를 나타내지 못할 수 있습니다.  
  
-   변환은 `int` 형식을 **long** 형식과 동일하게 나타내고, `unsigned int`를 `unsigned long`과 동일하게 나타냅니다.  
  
-   변환기는 문자 상수를 대상 개발 환경에 대한 집합과 다른 코드 값의 집합으로 변환할 수 있습니다.  대상 개발 환경의 속성을 확인하려면 대상 개발 환경용으로 작성된 응용 프로그램의 LIMITS.H에서 매크로 값을 확인합니다.  
  
-   식은 환경 조회를 수행해서는 안 되며 대상 컴퓨터의 구현 정보에서 영향을 받지 않아야 합니다.  
  
 전처리기 연산자 **defined**는 다음 구문과 같이 특수 상수 식에서 사용할 수 있습니다.  
  
 defined\( `identifier` \)  
  
 defined `identifier`  
  
 이 상수 식은 *identifier*가 현재 정의되어 있으면 true\(0이 아님\)로 간주되고, 그렇지 않으면 false\(0\)로 간주됩니다.  빈 텍스트로 정의된 식별자는 정의된 것으로 간주됩니다.  **defined** 지시문은 `#if` 및 `#elif` 지시문에서 사용할 수 있지만 다른 곳에서는 사용할 수 없습니다.  
  
 다음 예제에서 `#if` 및 `#endif` 지시문은 세 가지 함수 호출 중 하나의 컴파일을 제어합니다.  
  
```  
#if defined(CREDIT)  
    credit();  
#elif defined(DEBIT)  
    debit();  
#else  
    printerror();  
#endif  
```  
  
 `CREDIT` 식별자가 정의된 경우 `credit`에 대한 함수 호출이 컴파일됩니다.  `DEBIT` 식별자가 정의된 경우 `debit`에 대한 함수 호출이 컴파일됩니다.  식별자가 정의되지 않은 경우에는 `printerror`에 대한 호출이 컴파일됩니다.  C와 C\+\+에서 `CREDIT` 및 `credit`은 대\/소문자가 다르기 때문에 고유한 식별자입니다.  
  
 다음 예제의 조건부 컴파일 문은 `DLEVEL`이라는 이전에 정의된 기호화된 상수를 가정합니다.  
  
```  
#if DLEVEL > 5  
    #define SIGNAL  1  
    #if STACKUSE == 1  
        #define STACK   200  
    #else  
        #define STACK   100  
    #endif  
#else  
    #define SIGNAL  0  
    #if STACKUSE == 1  
        #define STACK   100  
    #else  
        #define STACK   50  
    #endif  
#endif  
#if DLEVEL == 0  
    #define STACK 0  
#elif DLEVEL == 1  
    #define STACK 100  
#elif DLEVEL > 5  
    display( debugptr );  
#else  
    #define STACK 200  
#endif  
```  
  
 첫 번째 `#if` 블록에는 중첩된 `#if`, `#else` 및 `#endif` 지시문의 두 집합이 표시됩니다.  `DLEVEL > 5`가 true인 경우에만 지시문의 첫 번째 집합이 처리됩니다.  그렇지 않으면 \#**else** 다음의 문이 처리됩니다.  
  
 두 번째 예제의 `#elif` 및 `#else` 지시문은 `DLEVEL` 값에 따라 네 가지 중 하나를 선택하는 데 사용됩니다.  `STACK` 상수는 `DLEVEL`의 정의에 따라 0, 100 또는 200으로 설정됩니다.  `DLEVEL`이 5보다 크면 다음 문이  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 컴파일되며 `STACK`은 정의되지 않습니다.  
  
 조건부 컴파일은 동일한 헤더 파일이 여러 번 포함되는 것을 방지하기 위해 일반적으로 사용됩니다.  헤더 파일에서 클래스가 자주 정의되는 C\+\+에서는 다음과 같은 구문을 사용하여 여러 정의를 방지할 수 있습니다.  
  
```  
/*  EXAMPLE.H - Example header file  */  
#if !defined( EXAMPLE_H )  
#define EXAMPLE_H  
  
class Example  
{  
...  
};  
  
#endif // !defined( EXAMPLE_H )  
```  
  
 앞의 코드에서는 기호화된 상수 `EXAMPLE_H`가 정의되어 있는지 여부를 확인합니다.  정의되어 있는 경우 해당 파일이 이미 포함되었으며 다시 처리될 필요가 없습니다.  정의되어 있지 않은 경우에는 `EXAMPLE_H` 상수가 이미 처리된 대로 EXAMPLE.H를 표시하도록 정의됩니다.  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)