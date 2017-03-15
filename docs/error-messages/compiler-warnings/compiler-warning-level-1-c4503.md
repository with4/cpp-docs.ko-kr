---
title: "컴파일러 경고 (수준 1) C4503 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: f999fcb73860bfd2fabb3484e78f313a32240dee
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4503"></a>컴파일러 경고(수준 1) C4503
'identifier': 데코레이팅된 이름 길이 초과 이름을 잘렸습니다.  
  
 데코레이팅된 이름은 컴파일러 한계 (4096) 보다 오래 되어 잘렸습니다. 이 경고와는 잘림을 방지, 하려면 인수 개수 또는 사용 되는 식별자의 이름 길이 줄이십시오.  
  
 여기서이 경고가 발생 합니다 한 경우 템플릿 특수화 된 반복 해 서으로 코드를 포함 하는 경우입니다.  예를 들어, (c + + 표준 라이브러리)에서 맵의 맵.  이 경우 형식 정의 해당 맵을 포함 하는 형식 (예: 구조체)를 만들 수 있습니다.  
  
 그러나 코드를 재구성 하지 결정할 수 있습니다.  C4503를 생성 하는 응용 프로그램을 제공할 수 있지만 잘린된 기호에서 링크 타임 오류를 발생 하는 경우 오류에 기호의 형식을 확인 하는 것이 어려울 수 됩니다.  디버깅도 더 어려워집니다. 디버거는 문제가 많은 것 매핑 이름 형식으로 기호 이름이 제공 됩니다.  그러나 프로그램의 정확성은 이름이 잘린된 영향을 받지.  
  
 다음 샘플에서는 C4503 오류가 생성 됩니다.  
  
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
  
 다음 샘플 C4503를 해결 하려면 코드를 다시 작성 하는 방법을 보여 줍니다.  
  
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
