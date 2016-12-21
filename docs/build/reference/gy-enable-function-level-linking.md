---
title: "/Gy(함수 수준 링크 사용) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking"
  - "/gy"
  - "VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gy 컴파일러 옵션[C++]"
  - "COMDAT 함수"
  - "함수 수준 링크 사용 컴파일러 옵션[C++]"
  - "Gy 컴파일러 옵션[C++]"
  - "-Gy 컴파일러 옵션[C++]"
  - "패키지 함수"
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gy(함수 수준 링크 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러가 개별 함수를 패키지된 함수의 형태로 패키지할 수 있습니다\(COMDATs\).  
  
## 구문  
  
```  
/Gy[-]  
```  
  
## 설명  
 링커에서는 함수가 별도의 COMDAT로 패키지되어 DLL 또는 .exe 파일 내에서 개별 함수를 제외하거나 개별 함수의 순서를 지정할 수 있습니다.  
  
 링커 옵션인 [\/OPT\(최적화\)](../../build/reference/opt-optimizations.md)를 사용하여 참조되지 않은 패키지 함수를 .exe 파일에서 제외할 수 있습니다.  
  
 링커 옵션인 [\/ORDER\(함수에 순서 지정\)](../../build/reference/order-put-functions-in-order.md)를 사용하여 패키지 함수를 지정한 순서로 .exe 파일에 포함할 수 있습니다.  
  
 인라인 함수는 호출로서 인스턴스화되는 경우 항상 패키지로 만들어집니다. 예를 들어 인라인을 사용하지 않거나 사용자가 함수 주소를 가져오는 경우가 여기에 해당합니다.  또한 클래스 선언에 정의된 C\+\+ 멤버 함수는 자동으로 패키지되지만 다른 함수는 그렇지 않으므로 다른 함수를 패키지 함수로 컴파일하려면 이 옵션을 선택해야 합니다.  
  
> [!NOTE]
>  편집하며 계속하기에 사용되는 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 사용하면 **\/Gy** 옵션이 자동으로 설정됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **함수 수준 링크 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)