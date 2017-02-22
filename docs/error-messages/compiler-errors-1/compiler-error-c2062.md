---
title: "컴파일러 오류 C2062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2062"
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

예기치 않은 'type' 형식입니다.  
  
 컴파일러가 형식 이름을 예상치 못했습니다.  
  
 다음 샘플에서는 C2062 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 C2062 오류는 생성자의 매개 변수 목록에서 정의되지 않은 형식을 컴파일러가 처리하는 방식으로 인해 발생할 수도 있습니다.  정의되지 않았거나 맞춤법이 틀린 형식을 컴파일러가 발견하면 생성자가 식으로 가정되므로 C2062 오류가 발생합니다.  이 문제를 해결하려면 생성자 매개 변수 목록에 정의된 형식만 사용해야 합니다.