---
title: "방법: /clr:safe로 마이그레이션(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 컴파일러 옵션[C++], /clr:safe로 마이그레이션"
  - "마이그레이션[C++], 안정형 어셈블리"
  - "Visual C++ 응용 프로그램 업그레이드, 안정형 어셈블리"
  - "안정형 어셈블리[C++], 마이그레이션"
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: /clr:safe로 마이그레이션(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 **\/clr:safe**를 사용하여 안정형 구성 요소를 생성할 수 있습니다. 이 옵션을 사용하면 각각의 비안정형 코드 구조체에 대해 컴파일러에서 오류가 생성됩니다.  
  
## 설명  
 안정성 오류의 발생 원인으로는 다음과 같은 것이 있습니다.  
  
-   네이티브 형식.  실제로 사용되지 않더라도 네이티브 클래스, 구조체, 포인터 또는 배열을 선언하면 컴파일이 수행되지 않습니다.  
  
-   전역 변수  
  
-   공용 언어 런타임 함수 호출을 비롯하여 관리되지 않는 라이브러리에 대한 함수 호출  
  
-   안정형 함수는 다운캐스팅을 위한 [static\_cast 연산자](../cpp/static-cast-operator.md)를 포함할 수 없습니다.  기본 형식 사이의 캐스팅에는 [static\_cast 연산자](../cpp/static-cast-operator.md)를 사용할 수 있지만 다운캐스팅에는 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)를 사용하거나 [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)로 구현되는 C 스타일 캐스트를 사용해야 합니다.  
  
-   안정형 함수에는 [reinterpret\_cast 연산자](../cpp/reinterpret-cast-operator.md) 또는 이에 해당하는 C 스타일 캐스트를 포함할 수 없습니다.  
  
-   안정형 함수는 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)에 대한 산술 연산을 수행할 수 없습니다.  이 포인터는 자체에만 할당되고 역참조됩니다.  
  
-   안정형 함수는 참조 형식에 대한 포인터만 throw하거나 catch합니다. 따라서 throw하기 전에 값 형식이 boxed 형식이 되어야 합니다.  
  
-   안정형 함수는 안정형 함수만 호출할 수 있습니다. 안정형 함수는 공용 언어 런타임을 호출할 수 없고 `AtEntry`\/`AtExit`를 포함하므로 전역 생성자를 사용할 수 없습니다.  
  
-   안정형 클래스에서는 <xref:System.Runtime.InteropServices.LayoutKind>를 사용할 수 없습니다.  
  
-   EXE를 빌드하는 경우 주 함수에서 매개 변수를 선언할 수 없으므로 <xref:System.Environment.GetCommandLineArgs%2A>를 사용하여 명령줄 인수를 검색해야 합니다.  
  
-   가상 함수에 대한 비가상 호출.  예를 들면 다음과 같습니다.  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 또한 확인할 수 있는 코드에는 다음 키워드를 사용할 수 없습니다.  
  
-   [unmanaged](../preprocessor/managed-unmanaged.md) 및 [pack](../preprocessor/pack.md) pragma  
  
-   [naked](../cpp/naked-cpp.md) 및 [align](../cpp/align-cpp.md) [\_\_declspec](../cpp/declspec.md) 한정자  
  
-   [\_\_asm](../assembler/inline/asm.md)  
  
-   [\_\_based](../cpp/based-grammar.md)  
  
-   [\_\_try](../cpp/try-except-statement.md) 및 `__except`  
  
## 참고 항목  
 [순수형 및 안정형 코드](../dotnet/pure-and-verifiable-code-cpp-cli.md)