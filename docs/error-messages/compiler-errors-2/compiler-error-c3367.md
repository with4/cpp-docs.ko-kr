---
title: "컴파일러 오류 C3367 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3367"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3367"
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3367
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'static\_member\_function': 바인딩되지 않은 대리자를 만드는 데 정적 함수를 사용할 수 없습니다.  
  
 바인딩되지 않은 대리자를 호출할 때는 개체의 인스턴스를 전달해야 합니다. 정적 멤버 함수는 클래스 이름을 통해 호출되기 때문에 인스턴스 멤버 함수와 함께 바인딩되지 않은 대리자만 인스턴스화할 수 있습니다.  
  
 자세한 내용은 [바인딩되지 않은 대리자](../../misc/unbound-delegates.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3367을 생성합니다.  
  
```  
// C3367.cpp // compile with: /clr ref struct R { void b() {} static void f() {} }; delegate void Del(R^); int main() { Del ^ a = gcnew Del(&R::b);   // OK Del ^ b = gcnew Del(&R::f);   // C3367 }  
```