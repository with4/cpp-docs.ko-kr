---
title: "auto 키워드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "auto"
  - "auto_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto 키워드"
  - "자동 저장소 클래스, auto 키워드"
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# auto 키워드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`auto` 키워드는 선언 지정자입니다.  그러나 C\+\+ 표준에는 이 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다.  [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] 전까지 `auto` 키워드에서는 *자동* 저장소 클래스에 있는 변수, 즉 지역 변수를 선언합니다.  [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)]부터 `auto` 키워드에서는 선언의 초기화 식에서 형식이 추론되는 변수를 선언합니다.  [\/Zc:auto &#91;\-](../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션은 `auto` 키워드의 의미를 제어합니다.  
  
## 구문  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## 설명  
 `auto` 키워드 정의는 C 프로그래밍 언어가 아닌 C\+\+ 프로그래밍 언어로 변경됩니다.  
  
 다음 항목에서는 `auto` 키워드 및 해당 컴파일러 옵션을 설명합니다.  
  
-   [auto](../cpp/auto-cpp.md)은 `auto` 키워드의 새 정의를 설명합니다.  
  
-   [\(NOTINBUILD\)auto Keyword \(Storage\-Class Specifier\)](http://msdn.microsoft.com/ko-kr/c7d0cecf-393d-4058-a6e6-b39e31d9edb0)는 `auto` 키워드의 원래 정의를 설명합니다.  
  
-   [\/Zc:auto\(변수 형식 추론\)](../build/reference/zc-auto-deduce-variable-type.md)은 사용할 `auto` 키워드의 정의를 컴파일러에 알리는 컴파일러 옵션을 설명합니다.  
  
## 참고 항목  
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)