---
title: "Platform, default, and cli Namespaces  (C++ Component Extensions) | Microsoft Docs"
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
  - "lang"
  - "cli"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lang namespace"
  - "cli namespace"
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Platform, default, and cli Namespaces  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

네임스페이스는 언어 요소의 이름을 한정하므로, 이름이 그렇지 않았다면 소스 코드의 다른 곳에 있는 같은 이름과 충돌하지 않습니다.  예를 들어 이름 충돌로 인해 컴파일러가 [상황에 맞는 키워드](../windows/context-sensitive-keywords-cpp-component-extensions.md)를 인식하지 못할 수 있습니다.  네임스페이스는 컴파일러에 의해 사용되지만 컴파일된 어셈블리에 유지되지 않습니다.  
  
## 모든 런타임  
 Visual C\+\+는 프로젝트를 만들 때 프로젝트에 대한 기본 네임스페이스를 제공합니다.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]에서는 .winmd 파일의 이름이 루트 네임스페이스의 이름과 일치해야 하지만, 네임스페이스의 이름을 수동으로 바꿀 수 있습니다.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 자세한 내용은 [네임스페이스 및 형식 표시 유형\(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx)을 참조하세요.  
  
### 요구 사항  
 컴파일러 옵션: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **구문**  
  
```  
using namespace cli;  
```  
  
 **설명**  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]는 `cli` 네임스페이스를 지원합니다.  **\/clr**로 컴파일할 때 구문 섹션에 `using` 문이 있는 것으로 간주됩니다.  
  
 다음 언어 기능은 `cli` 네임스페이스에 있습니다.  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md)  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### 요구 사항  
 컴파일러 옵션: **\/clr**  
  
### 예  
 **예제**  
  
 다음 코드 예제에서는 `cli` 네임스페이스의 기호를 코드의 사용자 정의 기호로 사용할 수 있음을 보여 줍니다.  그러나 그와 같이 할 경우 같은 이름의 `cli` 언어 요소에 대한 참조를 명시적 또는 묵시적으로 한정해야 합니다.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## 참고 항목  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)