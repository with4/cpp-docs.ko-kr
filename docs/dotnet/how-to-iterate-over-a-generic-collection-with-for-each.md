---
title: "방법: for each로 제네릭 컬렉션 반복 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "제네릭 컬렉션, 반복 처리"
ms.assetid: 00288d53-3d41-44d0-be5b-b3033456ceaa
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: for each로 제네릭 컬렉션 반복
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Generics](../windows/generics-cpp-component-extensions.md) Visual C\+\+ 기능을 사용 하면 제네릭 컬렉션을 만들 수 있습니다.  
  
## 예제  
 이 샘플에서는 사용 하는 방법을 보여 줍니다.  `for each`  간단한 제네릭 값 형식의 컬렉션입니다.  
  
```  
// for_each_generics.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <class T>  
public value struct MyArray : public IEnumerable<T> {     
  
   MyArray( array<T>^ d ) {  
      data = d;  
   }  
  
   ref struct enumerator : IEnumerator<T> {  
      enumerator( MyArray^ myArr ) {  
         colInst = myArr;  
         currentIndex = -1;  
      }  
  
      virtual bool MoveNext() = IEnumerator<T>::MoveNext {  
         if ( currentIndex < colInst->data->Length - 1 ) {  
            currentIndex++;  
            return true;  
         }  
  
         return false;  
      }  
  
      virtual property T Current {  
         T get() {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      property Object^ CurrentNonGeneric {  
         virtual Object^ get() = System::Collections::IEnumerator::Current::get {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      virtual void Reset() {}  
      ~enumerator() {}  
  
      MyArray^ colInst;  
      int currentIndex;  
   };  
  
   array<T>^ data;  
  
   virtual IEnumerator<T>^ GetEnumerator() {  
      return gcnew enumerator(*this);  
   }  
   virtual System::Collections::IEnumerator^ GetEnumeratorNonGeneric() = System::Collections::IEnumerable::GetEnumerator {  
      return gcnew enumerator(*this);  
   }  
};  
  
int main() {  
   MyArray<int> col = MyArray<int>( gcnew array<int>{10, 20, 30 } );  
  
   for each ( Object^ c in col )  
      Console::WriteLine((int)c);  
}  
```  
  
  **10**  
**20**  
**30**   
## 참고 항목  
 [for each, in](../dotnet/for-each-in.md)