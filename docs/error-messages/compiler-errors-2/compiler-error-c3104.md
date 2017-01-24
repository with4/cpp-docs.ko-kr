---
title: "컴파일러 오류 C3104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3104"
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

특성 인수가 잘못되었습니다.  
  
 특성에 잘못된 인수를 지정했습니다.  
  
 자세한 내용은 [Attribute Parameter Types](../../windows/attribute-parameter-types-cpp-component-extensions.md)를 참조하십시오.  
  
 이 오류는 Visual C\+\+ 2005에 대해 적용되었으며, 관리되는 배열을 사용자 지정 특성에 전달하는 경우 이 배열의 형식이 더 이상 집합체 초기화 목록에서 추론되지 않는다는 컴파일러 규칙의 결과로 발생할 수 있습니다.  컴파일러를 실행할 때 이니셜라이저 목록과 배열의 형식을 함께 지정해야 합니다.  
  
## 예제  
 다음 샘플에서는 C3104 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## 예제  
 다음 샘플에서는 C3104 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  
  
## 예제  
 다음 샘플에서는 C3104 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3104c.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
[ attribute(Class) ]  
public __gc class AnotherAttr {  
public:  
   AnotherAttr(Object* arr __gc[]) : var0(arr) {}  
   Object* var1 __gc[];  
   Object* var0 __gc[];  
};  
  
[ AnotherAttr( { __box(3.14159), S"pi" }, var1 = { S"a", S"b" } ) ]   // C3104  
public __gc class Class1 {};  
  
// OK  
[ AnotherAttr( new Object * __gc[] {__box(3.14159), S"pi" }, var1 = new Object * __gc[] { S"a", S"b" } ) ]  
public __gc class Class2 {};  
```