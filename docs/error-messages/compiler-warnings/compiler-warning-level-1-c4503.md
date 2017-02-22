---
title: "컴파일러 경고 (수준 1) C4503 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4503"
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 데코레이팅된 이름 길이를 초과했으므로 이름이 잘립니다.  
  
 데코레이팅된 이름이 컴파일러 한계인 4096자를 초과하므로 잘렸습니다.  이 경고가 발생하고 이름이 잘리는 것을 방지하려면 인수의 개수나 식별자에 사용한 이름의 길이를 줄입니다.  
  
 코드에 반복적으로 자체 특수화된 템플릿이 있는 경우에 이 경고가 발생할 수 있습니다.  표준 C\+\+ 라이브러리에 있는 map의 map를 예로 들 수 있습니다.  이러한 경우 typedef를 사용하여 map를 포함하는 형식\(구조체 등\)을 만들 수 있습니다.  
  
 그러나 코드를 재구성하지 않을 수도 있습니다.  C4503을 발생시키는 응용 프로그램을 제공할 수도 있지만, 링크할 때 이름이 잘린 기호에 대한 오류가 발생하는 경우 오류에서 기호의 형식을 확인하기가 어려워집니다.  또한 디버거에서 기호 이름을 형식 이름에 매핑하기가 어려우므로 디버깅도 어려워집니다.  그러나 이름이 잘리더라도 프로그램은 정확하게 동작합니다.  
  
 다음 샘플에서는 C4503 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 다음 샘플에서는 코드를 다시 작성하여 C4503을 해결하는 한 가지 방법을 보여 줍니다.  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```