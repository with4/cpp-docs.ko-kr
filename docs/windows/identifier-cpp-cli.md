---
title: "__identifier (C++/CLI) | Microsoft Docs"
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
  - "__identifier"
  - "__identifier_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__identifier keyword [C++]"
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __identifier (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

식별자로 Visual C\+\+ 키워드를 사용할 수 있습니다.  
  
## 모든 플랫폼  
 **구문**  
  
```  
  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
 **설명**  
  
 키워드가 아닌 식별자에 대한  `__identifier`  키워드를 사용할 수 있지만 스타일 상의 문제가 있습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
### 예제  
 **예제**  
  
 다음 예제에서는  `template`  라는 이름의 클래스가 C\#를 만들고 DLL로 배포합니다.    `template`  클래스를 사용하는 Visual C\+\+ 프로그램에서,   `__identifier`  키워드는  `template` 가 표준 c \+ \+ 키워드라는 사실을 숨깁니다.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **설명**  
  
 `__identifier`  키워드는  **\/clr**  및  **\/clr:oldSyntax**  컴파일러 옵션을 함께 사용할 수 있습니다.  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예제  
 **예제**  
  
 다음 예제에서는  `template`  라는 이름의 클래스가 C\#를 만들고 DLL로 배포합니다.    `template`  클래스를 사용하는 Visual C\+\+ 프로그램에서,   `__identifier`  키워드는  `template` 가 표준 c \+ \+ 키워드라는 사실을 숨깁니다.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)