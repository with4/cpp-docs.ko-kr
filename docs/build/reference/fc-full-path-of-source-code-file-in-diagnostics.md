---
title: "/FC(진단 소스 코드 파일의 전체 경로) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.UseFullPaths"
  - "/FC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FC 컴파일러 옵션[C++]"
  - "-FC 컴파일러 옵션[C++]"
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /FC(진단 소스 코드 파일의 전체 경로)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

진단을 통해 컴파일러에 전달된 소스 코드 파일의 전체 경로를 컴파일러에서 표시합니다.  
  
## 구문  
  
```  
/FC  
```  
  
## 설명  
 다음과 같은 코드 샘플을 생각해 볼 수 있습니다.  
  
```  
// compiler_option_FC.cpp  
int main( ) {  
   int i   // C2143  
}  
```  
  
 **\/FC**를 사용하지 않으면 진단 텍스트가 다음 진단 텍스트와 비슷하게 표시됩니다.  
  
-   compiler\_option\_FC.cpp\(5\) : error C2143: syntax error : missing ';' before '}'  
  
 **\/FC**를 사용하면 진단 텍스트가 다음 진단 텍스트와 비슷하게 표시됩니다.  
  
-   c:\\test\\compiler\_option\_FC.cpp\(5\) : error C2143: syntax error : missing ';' before '}'  
  
 \_\_FILE\_\_ 매크로를 사용할 때 파일 이름의 전체 경로를 표시하려는 경우에도 **\/FC**가 필요합니다.  \_\_FILE\_\_에 대한 자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)를 참조하십시오.  
  
 **\/FC** 옵션은 **\/ZI**에 포함됩니다.  **\/ZI**에 대한 자세한 내용은 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../../build/reference/z7-zi-zi-debug-information-format.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **C\/C\+\+** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **전체 경로 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)