---
title: "컴파일러 경고 (수준 1) C4091 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4091"
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'keyword' : 변수를 선언하지 않으면 'type' 왼쪽은 무시됩니다.  
  
 사용자가 변수를 선언하려고 의도했을 가능성이 있는 상황을 컴파일러가 발견했지만 컴파일러에서 변수를 선언할 수 없습니다.  
  
## 예제  
 사용자 정의 형식 선언의 시작 부분에 있는 `__declspec` 특성은 해당 형식의 변수에 적용됩니다.  C4091은 선언된 변수가 없음을 나타냅니다.  다음 샘플에서는 C4091 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## 예제  
 식별자가 형식 정의이면 이 식별자를 변수 이름으로 사용할 수 없습니다.  다음 샘플에서는 C4091 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```