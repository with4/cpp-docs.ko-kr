---
title: "/Zc:forScope(for 루프 범위의 강제 규칙) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ForceConformanceInForLoopScope"
  - "VC.Project.VCCLWCECompilerTool.ForceConformanceInForLoopScope"
  - "/zc:forScope"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc 컴파일러 옵션[C++]"
  - "규칙 컴파일러 옵션"
  - "Zc 컴파일러 옵션[C++]"
  - "-Zc 컴파일러 옵션[C++]"
ms.assetid: 3031f02d-3b14-4ad0-869e-22b0110c3aed
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:forScope(for 루프 범위의 강제 규칙)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft 확장\([\/Ze](../../cpp/for-statement-cpp.md)\)과 함께 [for](../../build/reference/za-ze-disable-language-extensions.md) 루프의 표준 C\+\+ 동작을 구현하는 데 사용됩니다.**\/Zc:forScope**는 기본적으로 설정되어 있습니다.  
  
## 구문  
  
```  
/Zc:forScope[-]  
```  
  
## 설명  
 **\/Zc:forScope\-** 옵션은 더 이상 사용되지 않으므로 이후 릴리스에서 제거될 예정입니다.**\/Zc:forScope\-**를 사용하면 사용 중단 경고 D9035가 발생합니다.  
  
 표준 동작은 **for** 루프의 이니셜라이저가 **for** 루프 후 범위를 벗어나는 것입니다.**\/Zc:forScope\-** 및 [\/Ze](../../build/reference/za-ze-disable-language-extensions.md)에서 **for** 루프의 이니셜라이저는 로컬 범위가 종료될 때까지 범위 내에 남아 있습니다.  
  
 다음 코드는 **\/Za**가 아니라 **\/Ze**에서 컴파일됩니다.  
  
```cpp  
// zc_forScope.cpp  
// compile by using: cl /Zc:forScope- /Za zc_forScope.cpp  
// C2065, D9035 expected  
int main() {  
    // Compile by using cl /Zc:forScope- zc_forScope.cpp  
    // to compile this non-standard code as-is.  
    // Uncomment the following line to resolve C2065 for /Za.  
    // int i;  
    for (int i = 0; i < 1; i++)  
        ;  
    i = 20;   // i has already gone out of scope under /Za  
}  
```  
  
 **\/Zc:forScope\-**를 사용하는 경우 이전 범위에서 만든 선언으로 인해 변수가 범위 내에 있으면 경고 C4288이 발생합니다\(기본적으로 설정되어 있지 않음\). 이를 증명하려면 예제 코드에서 `//` 문자를 제거하여 `int i`를 선언합니다.  
  
 [준수](../../preprocessor/conform.md) pragma를 사용하여 **\/Zc:forScope**의 런타임 동작을 수정할 수 있습니다.  
  
 기존 .pch 파일이 있는 프로젝트에서 **\/Zc:forScope\-**를 사용하면 **\/Zc:forScope\-**가 무시되고 기존 .pch 파일을 사용하여 계속 컴파일합니다. .pch 파일을 새로 생성하려면 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md)를 사용합니다.  
  
 Visual C\+\+의 규칙과 관련된 문제에 대한 자세한 내용은 [비표준 동작](../../cpp/nonstandard-behavior.md)을 참조하세요.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하세요.  
  
2.  탐색 창에서 **구성 속성**, **C\/C\+\+**, **언어** 속성 페이지를 엽니다.  
  
3.  **For 루프 범위 강제 규칙** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForceConformanceInForLoopScope%2A>을 참조하세요.  
  
## 참고 항목  
 [\/Zc\(규칙\)](../../build/reference/zc-conformance.md)   
 [\/Za, \/Ze\(언어 확장 사용 안 함\)](../../build/reference/za-ze-disable-language-extensions.md)