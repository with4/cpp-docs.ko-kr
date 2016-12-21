---
title: "방법: C# 인덱서 사용(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++, 인덱서"
  - "인덱서, C# 사용"
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: C# 인덱서 사용(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에는 인덱서가 포함되어 있지 않으며, 인덱싱된 속성이 있습니다.  C\# 인덱서를 사용하려면 인덱싱된 속성과 마찬가지로 인덱서에 액세스합니다.  
  
 인덱서에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [인덱서](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md)  
  
-   [방법: 인덱싱된 속성 사용](../misc/how-to-use-indexed-properties.md)  
  
## 예제  
 다음 C\# 프로그램에서는 인덱서를 정의합니다.  
  
```  
// consume_cs_indexers.cs  
// compile with: /target:library  
using System;  
public class IndexerClass {  
   private int [] myArray = new int[100];   
   public int this [int index] {   // Indexer declaration  
      get {  
         // Check the index limits.  
         if (index < 0 || index >= 100)  
            return 0;  
         else  
            return myArray[index];  
      }  
      set {  
         if (!(index < 0 || index >= 100))  
            myArray[index] = value;  
      }  
   }  
}  
/*  
// code to consume the indexer  
public class MainClass {  
   public static void Main() {  
      IndexerClass b = new IndexerClass();  
  
      // Call indexer to initialize elements 3 and 5  
      b[3] = 256;  
      b[5] = 1024;  
      for (int i = 0 ; i <= 10 ; i++)   
         Console.WriteLine("Element #{0} = {1}", i, b[i]);  
   }  
}  
*/  
```  
  
## 예제  
 다음 Visual C\+\+ 프로그램에서는 인덱서를 사용합니다.  
  
```  
// consume_cs_indexers_2.cpp  
// compile with: /clr  
#using "consume_cs_indexers.dll"  
using namespace System;  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->default[0] = 21;  
   for (int i = 0 ; i <= 10 ; i++)  
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);  
}  
```  
  
  **Element \#0 \= 21**  
**Element \#1 \= 0**  
**Element \#2 \= 0**  
**Element \#3 \= 0**  
**Element \#4 \= 0**  
**Element \#5 \= 0**  
**Element \#6 \= 0**  
**Element \#7 \= 0**  
**Element \#8 \= 0**  
**Element \#9 \= 0**  
**Element \#10 \= 0**   
## 참고 항목  
 [다른 .NET 언어와의 상호 운용성](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)