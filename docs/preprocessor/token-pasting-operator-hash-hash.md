---
title: "토큰 붙여넣기 연산자 (##) | Microsoft Docs"
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
  - "##"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "## 전처리 연산자"
  - "전처리기, 연산자"
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 토큰 붙여넣기 연산자 (##)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"병합" 연산자라고도 하는 이중 숫자 기호 또는 "토큰 붙여넣기" 연산자\(**\#\#**\)가 개체 형식 매크로와 함수 형식 매크로 모두에 사용됩니다.  이 연산자는 별도의 토큰이 단일 토큰으로 조인되도록 허용하므로 매크로 정의의 첫 번째 토큰 또는 마지막 토큰이 될 수 없습니다.  
  
 매크로 정의의 정식 매개 변수 앞이나 뒤에 토큰 붙여넣기 연산자가 오는 경우 정식 매개 변수가 즉시 확장되지 않은 실제 인수로 바뀝니다.  이러한 교체 이전에 해당 인수에서 매크로 확장이 수행되지 않습니다.  
  
 그런 다음 *token\-string*에서 토큰 붙여넣기 연산자가 발견될 때마다 해당 연산자가 제거되고 앞에 오거나 뒤에 오는 토큰이 연결됩니다.  결과 토큰은 올바른 토큰이어야 합니다.  올바른 토큰인 경우 해당 토큰은 매크로 이름을 나타낼 때 가능한 교체에 대해 검색됩니다.  식별자는 교체하기 전에 연결된 토큰이 프로그램에서 인식될 이름을 나타냅니다.  각 토큰은 프로그램 내 또는 컴파일러 명령줄 등 다른 곳에서 정의된 토큰을 나타냅니다.  연산자 앞이나 뒤의 공백은 선택 사항입니다.  
  
 이 예제에서는 문자열화 연산자와 토큰 붙여넣기 연산자를 모두 사용하여 프로그램 출력을 지정하는 방법을 보여 줍니다.  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 매크로가 다음과 같은 숫자 인수로 호출되는 경우  
  
```  
paster( 9 );  
```  
  
 매크로에서 다음을 생성하고  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 위는 다음이 됩니다.  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## 예제  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
  **token9 \= 9**   
## 참고 항목  
 [전처리 연산자](../preprocessor/preprocessor-operators.md)