---
title: "override  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "overriding, override keyword [C++]"
  - "override keyword [C++]"
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# override  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`override` 상황에 맞는 키워드는 형식의 멤버가 기본 클래스 또는 기본 인터페이스 멤버를 재정의해야 함을 나타냅니다.  
  
## 설명  
 `override` 키워드는 네이티브 대상\(기본 컴파일러 옵션\), Windows 런타임 대상\(**\/ZW** 컴파일러 옵션\) 또는 공용 언어 런타임 대상\(**\/clr** 컴파일러 옵션\)에 대해 컴파일할 때 유효합니다.  
  
 지정자 재정의에 대한 자세한 내용은 [override 지정자](../cpp/override-specifier.md) and [지정자 재정의 및 네이티브 컴파일](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md)을 참조하십시오.  
  
 대\/소문자를 구분하는 키워드에 대한 자세한 내용은 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 참조하십시오.  
  
## 예제  
 **예제**  
  
 다음 코드 예제에서는 `override`가 네이티브 컴파일에서 사용될 수도 있음을 보여줍니다.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **예제**  
  
 다음 코드 예제에서는 `override`가 Windows 런타임 컴파일에서 사용될 수 있음을 보여줍니다.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **요구 사항**  
  
 컴파일러 옵션: **\/ZW**  
  
 **예제**  
  
 다음 코드 예제에서는 `override`가 공용 언어 런타임 컴파일에서 사용될 수 있음을 보여줍니다.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **요구 사항**  
  
 컴파일러 옵션: **\/clr**  
  
## 참고 항목  
 [override 지정자](../cpp/override-specifier.md)   
 [Override 지정자](../windows/override-specifiers-cpp-component-extensions.md)