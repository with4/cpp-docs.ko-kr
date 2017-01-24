---
title: "/Za, /Ze(언어 확장 사용 안 함) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions"
  - "/za"
  - "/ze"
  - "VC.Project.VCCLCompilerTool.DisableLanguageExtensions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Za 컴파일러 옵션[C++]"
  - "/Ze 컴파일러 옵션[C++]"
  - "언어 확장 사용 안 함 컴파일러 옵션"
  - "언어 확장 사용"
  - "언어 확장"
  - "언어 확장, 컴파일러에서 사용 안 함"
  - "Za 컴파일러 옵션[C++]"
  - "-Za 컴파일러 옵션[C++]"
  - "Ze 컴파일러 옵션[C++]"
  - "-Ze 컴파일러 옵션[C++]"
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Za, /Ze(언어 확장 사용 안 함)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Za** 컴파일러 옵션은 ANSI C 또는 ANSI C\+\+와 호환되지 않는 언어 구문에 대한 오류를 내보냅니다.  기본값인 **\/Ze** 컴파일러 옵션은 Microsoft 확장을 사용합니다.  
  
## 구문  
  
```  
/Za  
/Ze  
```  
  
## 설명  
  
> [!NOTE]
>  **\/Ze** 옵션은 사용되지 않습니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 컴파일러는 ANSI C 또는 ANSI C\+\+ 표준에 지정된 기능 이외의 여러 기능을 제공합니다.  이러한 기능을 C 및 C\+\+에 대한 Microsoft 확장이라고 합니다.  이러한 확장은 **\/Ze** 옵션이 지정된 경우 사용할 수 있으며, **\/Za** 옵션이 지정된 경우에는 사용할 수 없습니다.  자세한 내용은 [C 및 C\+\+에 대한 Microsoft 확장](../../build/reference/microsoft-extensions-to-c-and-cpp.md)를 참조하십시오.  
  
 프로그램을 다른 환경에 이식하려는 경우에는 언어 확장을 사용하지 마십시오.  컴파일러는 확장된 키워드를 단순 식별자로 취급하고, 다른 Microsoft 확장을 사용하지 않으며, C 프로그램에 대한 미리 정의된 매크로 `__STDC__`를 자동으로 정의합니다.  
  
 **\/Za**와 함께 다른 컴파일러 옵션을 사용하면 컴파일러가 ANSI 규칙을 준수하는 방식에 영향을 줄 수 있습니다.  예를 들어, **\/Za** 및 [\/fp\(부동 소수점 동작 지정\)](../../build/reference/fp-specify-floating-point-behavior.md)를 함께 사용하면 예기치 않은 결과가 발생할 수 있습니다.  
  
 **\/Za**의 표준 동작을 알려면 [\/Zc](../../build/reference/zc-conformance.md) 컴파일러 옵션을 참조하십시오.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]의 규칙과 관련된 문제에 대한 자세한 내용은 [Visual C\+\+에서 호환성 및 규격 문제](../../misc/compatibility-and-compliance-issues-in-visual-cpp.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **언어** 속성 페이지를 클릭합니다.  
  
4.  **언어 확장 사용 안 함** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)