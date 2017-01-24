---
title: "컴파일러 오류 C2513 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2513"
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : '\=' 앞에 변수를 선언하지 않았습니다.  
  
 형식 지정자가 변수 식별자 없이 선언 부분에 표시됩니다.  
  
 다음 샘플에서는 C2513 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Visual Studio .NET 2003에서는 컴파일러 규칙에 따라 이제 형식 정의를 초기화할 수 없기 때문에 이 오류가 발생할 수도 있습니다.  표준에서는 형식 정의를 초기화할 수 없으므로 컴파일러 오류가 생성됩니다.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 또는 `typedef`를 삭제하여 집합체 이니셜라이저 목록으로 변수를 정의할 수 있습니다. 그러나 형식과 동일한 이름을 가진 변수가 만들어지고 형식 이름이 숨겨지므로 이렇게 하지 않는 것이 좋습니다.