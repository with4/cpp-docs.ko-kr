---
title: "컴파일러 오류 C3225 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3225"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3225"
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 오류 C3225
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg'에 대한 제네릭 형식 인수는 'type'일 수 없으며 값 형식이거나 참조 형식에 대한 핸들이어야 합니다.  
  
 제네릭 형식 인수가 올바른 형식이 아닙니다.  
  
 자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
 네이티브 형식을 사용하여 제네릭 형식을 인스턴스화할 수 없습니다.  다음 샘플에서는 C3225 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3225.cpp  
// compile with: /clr  
class A {};  
  
ref class B {};  
  
generic <class T>  
ref class C {};  
  
int main() {  
   C<A>^ c = gcnew C<A>;   // C3225  
   C<B^>^ c2 = gcnew C<B^>;   // OK  
}  
```  
  
## 예제  
 다음 샘플에서는 C\#을 사용하여 구성 요소를 만듭니다.  제약 조건에서 제네릭 형식을 값 형식으로만 인스턴스화할 수 있도록 지정하고 있습니다.  
  
```  
// C3225_b.cs  
// compile with: /target:library  
// a C# program  
public class MyList<T> where T: struct {}  
```  
  
## 예제  
 C\#으로 작성된 구성 요소를 사용하는 이 샘플에서는 <xref:System.Nullable> 이외의 값 형식으로만 MyList를 인스턴스화할 수 있다는 제약 조건을 위반합니다.  다음 샘플에서는 C3225 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3225_c.cpp  
// compile with: /clr  
#using "C3225_b.dll"  
ref class A {};  
value class B {};  
int main() {  
   MyList<A> x;   // C3225  
   MyList<B> y;   // OK  
}  
```