---
title: "상황에 맞는 키워드(C++ 구성 요소 확장) | Microsoft Docs"
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
  - "internal_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "상황에 맞는 키워드"
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 상황에 맞는 키워드(C++ 구성 요소 확장)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*상황에 맞는 키워드*는 특정 컨텍스트에서만 인식되는 언어 요소입니다.  특정 컨텍스트가 아닐 경우 상황에 맞는 키워드는 사용자 정의 기호일 수 있습니다.  
  
## 모든 런타임  
 **설명**  
  
 다음은 상황에 맞는 키워드의 목록입니다.  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each, in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`\([멤버 표시 유형](../misc/member-visibility.md) 참조\)  
  
-   [literal](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [property](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where`\([Generics](../windows/generics-cpp-component-extensions.md)의 일부\)  
  
 가독성을 위해 상황에 맞는 키워드를 사용자 정의 기호로만 제한할 수 있습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **설명**  
  
 \(이 기능에는 플랫폼별 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 \(이 기능에는 플랫폼별 설명이 없습니다.\)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 코드 예제는 적절한 컨텍스트에서 상황에 맞는 키워드 `property`를 사용하여 속성과 변수를 정의할 수 있음을 보여 줍니다.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Output**  
  
  **100**   
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)