---
title: "컴파일러 오류 C3673 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3673"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3673"
ms.assetid: bb6d2079-05af-4e2c-be0e-75c892e6c590
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3673
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 클래스에 복사 생성자가 없습니다.  
  
 CLR ref 형식의 개체를 복사하려면 사용자 정의 생성자가 필요합니다.  자세한 내용은 [참조 형식에 대한 C\+\+ 스택 의미 체계](../../dotnet/cpp-stack-semantics-for-reference-types.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3673 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3673.cpp  
// compile with: /clr  
public ref struct R {  
public:  
   R() {}  
   // Uncomment the following line to resolve.  
   // R(R% p) {}  
};  
  
int main() {  
   R r;  
   R s = r;   // C3673  
}  
```  
  
## 예제  
 다음 샘플에서는 C3673 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3673_b.cpp  
// compile with: /clr /c  
// C3673 expected  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   // Uncomment the following line to resolve.  
   // MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // OK, no arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // OK, named argument  
  
[MyAttr(123)]  
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]  
ref class ClassD {};   // Positional and named  
```