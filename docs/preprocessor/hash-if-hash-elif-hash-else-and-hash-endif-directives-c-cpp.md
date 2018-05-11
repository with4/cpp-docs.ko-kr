---
title: '##elif, if, #else, 및 #endif 지시문 (C/c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#else'
- '#endif'
- '#if'
- '#elif'
- defined
- __has_include
dev_langs:
- C++
helpviewer_keywords:
- '#elif directive'
- conditional compilation, directives
- endif directive (#endif)
- preprocessor, directives
- '#else directive'
- '#endif directive'
- if directive (#if)
- else directive (#else)
- '#if directive'
- elif directive (#elif)
- defined directive
ms.assetid: c77a175f-6ca8-47d4-8df9-7bac5943d01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a9d4f941298159b8a3ea1aa3fe37efd1e6dc68ab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="if-elif-else-and-endif-directives-cc"></a>#if, #elif, #else, and #endif 지시문 (C/C++)
`#if` 지시문은 `#elif`, `#else` 및 `#endif` 지시문과 함께 소스 파일 부분들의 컴파일을 제어합니다. `#if` 뒤에 작성하는 식에 0이 아닌 값이 있는 경우 `#if` 지시문 바로 다음에 나오는 줄 그룹은 변환 단위에서 유지됩니다.  
  
## <a name="grammar"></a>문법  
 *조건부* :  
 *if 부분 elif 부품*opt*else 부분*opt*endif 줄*  
  
 *if-part* :  
 *if 줄 텍스트*  
  
 *if-line* :  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif-parts* :  
 *elif 줄 텍스트*  
  
 *elif 부품 elif 줄 텍스트*  
  
 *elif-line* :  
 **#elif**  *constant-expression*  
  
 *else-part* :  
 *다른 줄 텍스트*  
  
 *else-line* :  
 `#else`  
  
 *endif-line* :  
 `#endif`  
  
 소스 파일의 각 `#if` 지시문은 닫는 `#endif` 지시문과 일치해야 합니다. 원하는 수의 `#elif` 지시문이 `#if` 및 `#endif` 지시문 사이에 나타날 수 있지만 `#else` 지시문은 하나만 허용됩니다. `#else` 지시문(있을 경우)은 `#endif` 앞에 있는 마지막 지시문이어야 합니다.  
  
 `#if`, `#elif`, `#else` 및 `#endif` 지시문은 다른 `#if` 지시문의 텍스트 부분에서 중첩될 수 있습니다. 중첩된 각 `#else`, `#elif` 또는 `#endif` 지시문은 가장 가까운 이전 `#if` 지시문에 속합니다.  
  
 모든 조건부 컴파일 지시문와 같은 `#if` 및 **#ifdef**, 닫는와 일치 시켜야 `#endif` 지시문 전에 파일 끝에; 그렇지 않으면 오류 메시지가 생성 됩니다. 조건부 컴파일 지시문이 포함 파일에 포함된 경우 동일한 조건을 만족해야 합니다. 포함 파일의 끝에 일치하지 않는 조건부 컴파일 지시문이 없어야 합니다.  
  
 매크로 대체는 다음에 나오는 명령줄의 일부 내에서 수행는 `#elif` 매크로 호출에 사용할 수 있도록 명령에서 *문*합니다.  
  
 전처리기의 지정 된 항목 중 하나를 선택 합니다. *텍스트* 추가 처리를 위해 합니다. 에 지정 된 블록이 *텍스트* 임의의 텍스트 시퀀스 될 수 있습니다. 두 줄 이상을 차지할 수 있습니다. 일반적으로 *텍스트* 컴파일러 또는 전처리기에 의미가 있는 프로그램 텍스트입니다.  
  
 전처리기는 선택한 처리 *텍스트* 컴파일러에 전달 합니다. 경우 *텍스트* 전처리기 지시문, 전처리기가 해당 지시문을 포함 합니다. 전처리기에서 선택한 텍스트 블록만 컴파일됩니다.  
  
 전처리기는 단일 선택 *텍스트* 항목 다음에 나오는 각 상수 식 평가 하 여 `#if` 또는 `#elif` 상수 식이 true (0이 아님)를 찾을 때까지 지시문입니다. 모든 텍스트를 선택 (부터는 다른 전처리기 지시문을 포함 하 여 **#**) 연결 된 최대 `#elif`, `#else`, 또는 `#endif`합니다.  
  
 하는 경우의 항목을 모두 *문* 경우에 없는 경우 또는 `#elif` 지시문, 전처리기가 다음의 텍스트 블록을 선택는 `#else` 절. 경우는 `#else` 절을 생략 하면 및 함수의 모든 인스턴스의 *문* 에 `#if` 블록은 false, 텍스트 블록이 없습니다. 선택 합니다.  
  
 *문* 는 이러한 추가 제한이 있는 정수 상수 식:  
  
-   식은 정수 계열 형식 이어야 하며 문자 상수 정수 상수만 포함 될 수 있습니다 및 **정의** 연산자입니다.  
  
-   식에서는 `sizeof` 또는 형식 캐스팅 연산자를 사용할 수 없습니다.  
  
-   대상 개발 환경은 모든 범위의 정수를 나타내지 못할 수 있습니다.  
  
-   변환 유형을 나타내는 `int` 형식과 동일 **긴**, 및 `unsigned int` 동일 `unsigned long`합니다.  
  
-   변환기는 문자 상수를 대상 개발 환경에 대한 집합과 다른 코드 값의 집합으로 변환할 수 있습니다. 대상 개발 환경의 속성을 확인하려면 대상 개발 환경용으로 작성된 응용 프로그램의 LIMITS.H에서 매크로 값을 확인합니다.  
  
-   식은 환경 조회를 수행해서는 안 되며 대상 컴퓨터의 구현 정보에서 영향을 받지 않아야 합니다.  

## <a name="defined"></a>정의  
 전처리기 연산자 **정의** 다음 구문을 사용 하 여 표시 된 것과 같이 특수 상수 식에 사용할 수 있습니다.  
  
 defined( `identifier` )  
  
 defined `identifier`  
  
 이 상수 식은 true (0이 아님)으로 간주 됩니다는 *식별자* 현재 정의 되어 있으면 조건이 false, (0). 빈 텍스트로 정의된 식별자는 정의된 것으로 간주됩니다. **정의** 지시문에서 사용할 수는 `#if` 및 `#elif` 지시문을 사용 하지만 다른 위치입니다.  
  
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
  
 `credit` 식별자가 정의된 경우 `CREDIT`에 대한 함수 호출이 컴파일됩니다. `DEBIT` 식별자가 정의된 경우 `debit`에 대한 함수 호출이 컴파일됩니다. 식별자가 정의되지 않은 경우에는 `printerror`에 대한 호출이 컴파일됩니다. C와 C++에서 `CREDIT` 및 `credit`은 대/소문자가 다르기 때문에 고유한 식별자입니다.  
  
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
  
 첫 번째 `#if` 블록에는 중첩된 `#if`, `#else` 및 `#endif` 지시문의 두 집합이 표시됩니다. `DLEVEL > 5`가 true인 경우에만 지시문의 첫 번째 집합이 처리됩니다. 그렇지 않으면 # 다음의 문이**다른** 처리 됩니다.  
  
 두 번째 예제의 `#elif` 및 `#else` 지시문은 `DLEVEL` 값에 따라 네 가지 중 하나를 선택하는 데 사용됩니다. `STACK` 상수는 `DLEVEL`의 정의에 따라 0, 100 또는 200으로 설정됩니다. `DLEVEL`이 5보다 크면 다음 문이  
  
```  
#elif DLEVEL > 5  
display(debugptr);  
```  
  
 컴파일되며 `STACK`은 정의되지 않습니다.  
  
 조건부 컴파일은 동일한 헤더 파일이 여러 번 포함되는 것을 방지하기 위해 일반적으로 사용됩니다. 헤더 파일에서 클래스가 자주 정의되는 C++에서는 다음과 같은 구문을 사용하여 여러 정의를 방지할 수 있습니다.  
  
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
  
 앞의 코드에서는 기호화된 상수 `EXAMPLE_H`가 정의되어 있는지 여부를 확인합니다. 정의되어 있는 경우 해당 파일이 이미 포함되었으며 다시 처리될 필요가 없습니다. 정의되어 있지 않은 경우에는 `EXAMPLE_H` 상수가 이미 처리된 대로 EXAMPLE.H를 표시하도록 정의됩니다.  

## <a name="hasinclude"></a>__has_include
**Visual Studio 2017 버전 15.3 이상**: 라이브러리 헤더를 포함 하기 위해 사용할 수 있는지 확인 합니다.  

```cpp
#ifdef __has_include
#  if __has_include(<filesystem>)
#    include <filesystem>
#    define have_filesystem 1
#  elif __has_include(<experimental/filesystem>)
#    include <experimental/filesystem>
#    define have_filesystem 1
#    define experimental_filesystem
#  else
#    define have_filesystem 0
#  endif
#endif
```
  
## <a name="see-also"></a>참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)