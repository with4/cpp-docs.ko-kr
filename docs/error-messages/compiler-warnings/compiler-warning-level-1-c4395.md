---
title: "컴파일러 경고 (수준 1) C4395 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4395"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4395"
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4395
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 멤버 함수가 initonly 데이터 멤버 'member'의 복사본에 대해 호출됩니다.  
  
 멤버 함수가 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버에 대해 호출되었습니다.  C4395 경고는 함수에서 **initonly** 데이터 멤버를 수정할 수 없음을 나타냅니다.  
  
 다음 샘플에서는 C4395 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4395.cpp  
// compile with: /W1 /clr  
public value class V {  
public:  
   V(int data) : m_data(data) {}  
  
   void Mutate() {  
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);  
      m_data *= 2;  
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);  
   }  
  
   int m_data;  
};  
  
public ref class R {  
public:  
   static void f() {  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
      v.Mutate();   // C4395  
      System::Console::WriteLine("v.m_data = {0}", v.m_data);  
   }  
  
private:  
   initonly static V v = V(4);  
};  
  
int main() {  
   R::f();  
}  
```