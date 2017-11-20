---
title: "방법: C# 인덱서 사용 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1e7938022bfe2ba1a8f97420a217590de659d9e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-consume-a-c-indexer-ccli"></a>방법: C# 인덱서 사용(C++/CLI)
Visual c + + 인덱서가; 포함 되어 있지 않습니다. 인덱싱된 속성에 해당 합니다. C# 인덱서를 사용 하려면 인덱싱된 속성 처럼 인덱서를 액세스 합니다.  
  
 인덱서에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [인덱서](https://msdn.microsoft.com/library/6x16t2tx.aspx)  
  
## <a name="example"></a>예제  
 다음 C# 프로그램 인덱서를 정의합니다.  
  
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
  
## <a name="example"></a>예제  
 이 Visual c + + 프로그램에서는 인덱서를 사용 합니다.  
  
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
  
```Output  
Element #0 = 21  
Element #1 = 0  
Element #2 = 0  
Element #3 = 0  
Element #4 = 0  
Element #5 = 0  
Element #6 = 0  
Element #7 = 0  
Element #8 = 0  
Element #9 = 0  
Element #10 = 0  
```  
  
## <a name="see-also"></a>참고 항목  
 [다른 .NET 언어와의 상호 운용성(C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)