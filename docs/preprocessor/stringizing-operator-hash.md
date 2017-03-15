---
title: "문자열화 연산자 (#) | Microsoft Docs"
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
  - "#"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "# 전처리 연산자"
  - "인수[C++], 문자열로 변환"
  - "매크로[C++], 매개 변수를 문자열로 변환"
  - "전처리기"
  - "전처리기, 연산자"
  - "문자열 리터럴, 매크로를 매개 변수로 변환"
  - "문자열화 연산자"
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 문자열화 연산자 (#)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

숫자 기호 또는 "문자열화" 연산자\(**\#**\)는 매개 변수 정의 확장 없이 매크로 매개 변수를 문자열 리터럴로 변환합니다.  인수를 사용하는 매크로에만 사용됩니다.  매크로 호출이 전달하는 실제 인수가 매크로 정의에서 형식 매개 변수 앞에 나오는 경우, 해당 인수는 따옴표로 묶이고 문자열 리터럴로 취급됩니다.  해당 문자열 리터럴은 매크로 정의에서 문자열화된 연산자와 형식적 매개 변수의 조합이 발생할 때마다 이를 대체합니다.  
  
> [!NOTE]
>  예전에 확장된 매크로 형식 인수가 문자열 리터럴 및 문자 상수 내부에 표시되던 Microsoft C\(6.0 및 이전 버전\) ANSI C 표준 확장은 더 이상 지원되지 않습니다.  이 확장에 의존하는 코드는 문자열화\(**\#**\) 연산자를 사용하여 다시 작성해야 합니다.  
  
 실제 인수의 첫 번째 토큰 앞에 오는 공백 및 실제 인수의 마지막 토큰 뒤에 오는 공백은 무시됩니다.  실제 인수의 토큰 사이의 공백은 결과 문자열 리터럴에서 단일 공백으로 줄어듭니다.  따라서 실제 인수의 두 토큰 사이에 주석이 있을 경우 해당 주석은 단일 공백으로 줄어듭니다.  결과 문자열 리터럴은 공백으로만 구분된 모든 인접 문자열 리터럴을 자동으로 연결한 것입니다.  
  
 또한 인수에 포함된 문자가 문자열 리터럴\(예: 따옴표\(**"**\) 또는 백슬래시\(**\\**\) 문자\)에 사용될 때 일반적으로 이스케이프 시퀀스를 필요로 할 경우, 필요한 이스케이프 백슬래시가 해당 문자 앞에 자동으로 삽입됩니다.  
  
 Visual C\+\+ 문자열화 연산자는 일부 상황에서 예상대로 동작하지 않을 수 있습니다. 자세한 내용은 [16.3.2 \# 연산자](../misc/16-3-2-the-hash-operator.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 매크로를 호출하는 문자열화 연산자 및 main 함수 호출을 포함하는 매크로 정의를 보여 줍니다.  
  
 이러한 호출은 전처리가 수행되는 동안 확장되어 다음 코드를 만듭니다.  
  
```  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
  **printf 함수 호출에서 따옴표로 묶음**  
**"화면에 출력할 때 따옴표로 묶음"**  
**"This: \\"는 이스케이프된 큰따옴표\("\)를 출력**   
## 예제  
 다음 예제에서는 매크로 매개 변수를 확장하는 방법을 보여 줍니다.  
  
```  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## 참고 항목  
 [전처리 연산자](../preprocessor/preprocessor-operators.md)