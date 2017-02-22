---
title: "컴파일러 오류 C3222 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3222"
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter': 제네릭 함수 또는 관리되는 또는 WinRT 형식의 멤버 함수에 대한 기본 인수를 선언할 수 없습니다.  
  
 기본 인수를 사용하는 메서드 매개 변수를 선언할 수 없습니다.  메서드의 오버로드된 형식은 이 문제를 해결하는 한 가지 방법입니다.  즉, 매개 변수 없이 동일한 이름을 사용하는 메서드를 정의한 다음 메서드 본문에서 변수를 초기화합니다.  
  
 다음 샘플에서는 C3222를 생성합니다.  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
  
 다음 샘플에서는 C3222를 생성합니다.  
  
```  
// C3222.cpp  
// compile with: /clr:oldSyntax  
public __gc class G {  
   void f( int n = 0 );   // C3222  
};  
```