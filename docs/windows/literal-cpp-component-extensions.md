---
title: "literal (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "literal"
  - "literal_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "literal keyword [C++]"
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# literal (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\/clr**  컴파일에서   `literal` 로 표시 된 변수\(데이터 요소\)는  `static const`  변수의 네이티브와 동일합니다.  
  
## 모든 플랫폼  
 **설명**  
  
 \(모든 런타임에 적용되는 이 언어 기능에 대한 설명이 없습니다.\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 \(이 언어 기능에는 Windows 런타임에만 적용되는 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## 공용 언어 런타임  
  
## 설명  
 `literal`  로 표시 된 데이터 멤버는 선언할 때 초기화해야 하며, 정수 계열 상수, 열거형 또는 문자열 형식의 값이어야 합니다.  const 정적 데이터 멤버의 형식으로 초기화 식의 형식에서 변환 사용자 정의 변환을 필요로하지 않아야합니다.  
  
 메모리가 런타임에 문자 필드에 할당되지 않습니다; 컴파일러는 클래스의 메타 데이터에 값을 삽입합니다.  
  
 `static const` 라고 표시된 변수는 기타 컴파일러에 대한 메타 데이터에 사용할 수 없습니다.  
  
 자세한 내용은 [정적](../misc/static-cpp.md) 및 [const](../cpp/const-cpp.md)를 참조하십시오.  
  
 `literal`는 상황에 맞는 키워드입니다.  자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 이 예제는  `literal`  변수가  `static` 을 의미함을 보여줍니다.  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## 예제  
 다음 예제에서는 리터럴 메타 데이터가 미치는 영향을 보여줍니다.  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 `sc`  및  `lit` 에 대한 메타 데이터에서 차이점을 알 수 있습니다:  `modopt`  지시문은  `sc` 에 적용 되어 , 다른 컴파일러에 의해 의미가 무시될 수 있습니다.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## 예제  
 C\#에서 작성된 다음 샘플에서는 이전 샘플에서 만든 메타 데이터를 참조하고  `literal`  및  `static const`  변수의 영향을 보여줍니다 :  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## 요구 사항  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)