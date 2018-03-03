---
title: "제네릭 사용 (C + + /cli CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], consuming from .NET languages
ms.assetid: e6330ef5-e907-432e-b527-7a22f5899639
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f5a767995ce0484552d96429573e0b355820207
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="consuming-generics-ccli"></a>제네릭 사용(C++/CLI)
한 .NET 언어로 작성된 제네릭은 다른 .NET 언어에서 사용할 수 있습니다. 템플릿과는 달리, 컴파일된 어셈블리의 제네릭은 여전히 제네릭으로 남아있습니다. 따라서 제네릭 형식이 정의된 어셈블리보다 다른 어셈블리 및 다른 언어로 제네릭 형식을 인스턴스화할 수 있습니다.  
  
## <a name="example"></a>예  
  
### <a name="description"></a>설명  
 이 예제에서는 C#에 정의된 제네릭 클래스를 보여 줍니다.  
  
### <a name="code"></a>코드  
  
```  
// consuming_generics_from_other_NET_languages.cs  
// compile with: /target:library  
// a C# program  
public class CircularList<ItemType> {  
   class ListNode    {  
      public ItemType m_item;  
      public ListNode next;  
      public ListNode(ItemType item) {  
         m_item = item;  
      }  
   }  
  
   ListNode first, last;  
  
   public CircularList() {}  
  
   public void Add(ItemType item) {  
      ListNode newnode = new ListNode(item);  
      if (first == null) {  
         first = last = newnode;  
         first.next = newnode;  
         last.next = first;  
      }  
      else {  
         newnode.next = first;  
         first = newnode;  
         last.next = first;  
      }   
   }  
  
   public void Remove(ItemType item) {  
      ListNode iter = first;  
      if (first.m_item.Equals( item )) {  
         first =   
         last.next = first.next;  
      }  
      for ( ; iter != last ; iter = iter.next )  
         if (iter.next.m_item.Equals( item )) {  
              if (iter.next == last)  
                  last = iter;  
              iter.next = iter.next.next;  
              return;  
          }  
   }  
  
   public void PrintAll() {  
      ListNode iter = first;  
      do {  
         System.Console.WriteLine( iter.m_item );  
         iter = iter.next;  
      } while (iter != last);  
   }  
}  
```  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 이 예제에서는 C#에서 작성된 어셈블리를 사용합니다.  
  
### <a name="code"></a>코드  
  
```  
// consuming_generics_from_other_NET_languages_2.cpp  
// compile with: /clr  
#using <consuming_generics_from_other_NET_languages.dll>  
using namespace System;  
class NativeClass {};  
ref class MgdClass {};  
  
int main() {  
   CircularList<int>^ circ1 = gcnew CircularList<int>();  
   CircularList<MgdClass^>^ circ2 = gcnew CircularList<MgdClass^>();  
  
   for (int i = 0 ; i < 100 ; i += 10)  
      circ1->Add(i);  
   circ1->Remove(50);  
   circ1->PrintAll();  
}  
```  
  
### <a name="output"></a>출력  
  
```  
90  
80  
70  
60  
40  
30  
20  
10  
```  
  
## <a name="see-also"></a>참고 항목  
 [제네릭](../windows/generics-cpp-component-extensions.md)