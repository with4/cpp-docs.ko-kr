---
title: "컴파일러 경고(수준 1) C4817 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4817"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4817"
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고(수준 1) C4817
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': 이 멤버에 액세스하기 위해 '.'를 사용할 수 없습니다. 컴파일러는 '\-\>'로 바뀝니다.  
  
 잘못된 멤버 액세스 연산자가 사용되었습니다.  
  
## 예제  
 다음 샘플에서는 C4817을 생성합니다.  
  
```  
// C4817.cpp // compile with: /clr /W1 using namespace System; int main() { array<Int32> ^ a = gcnew array<Int32>(100); Console::WriteLine( a.Length );   // C4817 Console::WriteLine( a->Length );   // OK }  
```  
  
## 예제  
 **\/clr:oldSyntax**를 사용하는 경우에도 C4817이 생성될 수 있습니다. 다음 샘플에서는 C4817을 생성합니다.  
  
```  
// C4817_b.cpp // compile with: /clr:oldSyntax /W1 using namespace System; int main() { Int32 a[] = new Int32[11]; Console::WriteLine( a.Length ); // Console::WriteLine( a->Length ); }  
```