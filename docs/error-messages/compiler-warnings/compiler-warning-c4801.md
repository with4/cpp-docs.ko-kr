---
title: "컴파일러 경고 C4801 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4801"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4801"
ms.assetid: 05b29dff-15ef-42ca-9712-dc993afc4fd6
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 C4801
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

참조로 반환하면 확인할 수 없습니다. reason  
  
 추적 참조를 지역 변수에 저장한 다음 이를 안전하게 반환할 수 없습니다.  
  
 참조는 작성 시점에서 반환 시점까지 검증 도구로 추적할 수 있고 클래스의 멤버 또는 배열의 요소에 대한 참조인 경우에만 안전하게 반환할 수 있습니다.  
  
 자세한 내용은 [Peverify.exe\(PEVerify 도구\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)을 참조하십시오.  
  
 참조의 안정성을 확인할 수 있으려면 작성에서 반환 시점까지 참조가 스택에 있어야 합니다.  
  
 C4801은 항상 오류로서 발생합니다.  `#pragma warning` 또는 **\/wd**를 사용하여 이 경고를 해제할 수 있습니다. 자세한 내용은 [경고](../../preprocessor/warning.md) 또는 [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won\(경고 수준\)](../../build/reference/compiler-option-warning-level.md)을 참조하십시오.  
  
## 예제  
 C4801은 사용된 주소를 검증 도구에서 확인할 수 없기 때문에 안전성을 확인할 수 없는 참조로 간주해야 하는 경우에 발생합니다.  다음 샘플에서는 C4801 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4801.cpp  
// compile with: /clr:safe /c  
int% f(int% p) {  
   return p;   // C4801  
}  
```  
  
## 예제  
 다음 샘플에서는 C4801 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4801_b.cpp  
// compile with: /clr:safe /c  
  
int% f(int i, array<int>^ ar) {  
   int x;  
   int% bri = x;   // cannot return a byref to a local.  
   if (i < ar->Length) {  
      bri = ar[i];   // this byref is ok.  
   }  
  
   return bri;   // C4801 not returned within the basic block  
}  
```  
  
## 예제  
 C4801은 역참조 후 try 블록에 참조 값을 반환하려는 경우에도 발생할 수 있습니다.  이렇게 하면 try 블록의 끝에서 스택이 지워지므로 스택의 모든 반환 값이 소멸되어 코드의 안정성을 확인할 수 없습니다.  대신, 참조 형식을 역참조하고 이를 변수에 할당하면 예외가 throw되지 않습니다.  그런 다음 함수의 끝에서 참조 형식을 다시 역참조하고 이를 반환합니다.  
  
 다음 샘플에서는 C4801 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4801_c.cpp  
// compile with: /clr:safe  
using namespace System;  
  
ref class StackEmptyException : public System::Exception {};  
ref class StackFullException : public System::Exception {};  
  
template <typename T>  
ref struct Stack {  
  
   Stack() {  
      topElem = -1;   // initialize stack  
      stackPtr = gcnew array<T>(10);  
   }  
  
   void push(const T%);  
   T% top();  
  
private:  
   int topElem;    
   array<T>^ stackPtr;    
};  
  
template <typename T>   
T% Stack<T>::top() {  
   try {  
      return stackPtr[topElem];   // C4801  
      // Try the following line instead.  
      // T% deadstore = stackPtr[topElem] ;  
   }  
  
   catch (System::IndexOutOfRangeException ^ e) {  
      throw gcnew StackEmptyException();  
   }  
  
   catch (System::Exception ^ e) {  
      throw;  
   }  
  
   return stackPtr[topElem] ;  
}  
  
int main() {  
   typedef Stack<Int32> IntStack;  
   IntStack ^ is = gcnew IntStack();  
  
   int i = 1;  
   while (1) {  
      try {  
         is->push(i++);  
      }  
      catch (System::Exception ^ e) {  
         break;  
      }  
      Console::Write("{0} ", is->top());  
   }  
}  
```