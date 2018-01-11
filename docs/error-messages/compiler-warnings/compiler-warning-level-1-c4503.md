---
title: "컴파일러 경고 (수준 1) C4503 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4503
dev_langs: C++
helpviewer_keywords: C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f8af13ffdcd71d760a180340a79a863cecb5e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4503"></a>컴파일러 경고(수준 1) C4503
'identifier': 데코레이팅된 이름 길이 초과 했으므로 이름이 잘립니다  
  
 데코 레이트 된 이름 (4096) 컴파일러 한계를 초과 하 고 잘렸습니다. 이 경고와는 잘림을 방지, 하려면 인수의 수 나 사용 되는 식별자 이름 길이 줄입니다.  
  
 한 가지 상황은 여기서이 경고가 발생 합니다는 코드에 포함 된 경우 템플릿 특수화 된 반복 해 서 합니다.  예를 들어 지도 (표준 c + + 라이브러리)에서 맵.  이 경우 프로그램 typedefs 해당 맵을 포함 하는 형식 (예: 구조체)를 만들 수 있습니다.  
  
 그러나 코드를 재구성 하지 결정할 수도 있습니다.  C4503을 생성 하는 응용 프로그램 수 있지만 잘린된 기호에 링크 타임 오류를 발생 한 경우 오류에 기호의 형식을 결정 하는 것이 어려울 수 됩니다.  디버깅도 더 어렵습니다. 디버거가 기호 이름을 입력 하는 이름을 문제가 많은 것 매핑 제공 됩니다.  그러나 프로그램의 정확성 영향을 받지 않습니다 잘린된 이름입니다.  
  
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
  
 다음 샘플에서는 C4503를 해결 하려면 코드를 다시 작성 하는 방법을 보여 줍니다.  
  
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