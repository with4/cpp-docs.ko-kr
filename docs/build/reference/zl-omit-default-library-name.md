---
title: "/Zl(기본 라이브러리 이름 생략) | Microsoft Docs"
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
  - "/zi"
  - "VC.Project.VCCLCompilerTool.OmitDefaultLibName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zl 컴파일러 옵션[C++]"
  - "기본 라이브러리, 이름 생략"
  - "기본 라이브러리 이름 생략 컴파일러 옵션"
  - "ZI 컴파일러 옵션"
  - "-Zl 컴파일러 옵션[C++]"
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zl(기본 라이브러리 이름 생략)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.obj 파일에서 기본 C 런타임 라이브러리 이름을 생략합니다.  기본적으로 컴파일러는 라이브러리의 이름을 .obj 파일에 넣어 링커를 정확한 라이브러리로 안내합니다.  
  
## 구문  
  
```  
/Zl  
```  
  
## 설명  
 기본 라이브러리에 대한 자세한 내용은 [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md)을 참조하십시오.  
  
 **\/Zl**을 사용하면 라이브러리에 넣으려는 .obj 파일을 컴파일할 수 있습니다.  라이브러리 이름을 생략하는 경우 하나의 .obj 파일에서 보면 절약되는 공간은 얼마 되지 않지만, 많은 개체 모듈을 가지고 있는 라이브러리에서 보면 절약되는 총 공간의 양은 상당합니다.  
  
 이 옵션은 고급 옵션입니다.  이 옵션을 설정하면 응용 프로그램에 필요한 특정 C 런타임 라이브러리 지원이 제거될 수 있습니다. 따라서 응용 프로그램에 이 지원이 필요한 경우 링크 타임 오류가 발생할 수 있습니다.  이 옵션을 사용하려면 필요한 구성 요소를 다른 방식으로 제공해야 합니다.  
  
 링커가 모든 .obj 파일에서 라이브러리 참조를 무시하도록 [\/NODEFAULTLIB\(라이브러리 무시\)](../../build/reference/nodefaultlib-ignore-libraries.md) 사용을 지시할 수 있습니다.  
  
 자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조하십시오.  
  
 **\/Zl**을 사용하여 컴파일하면 `_VC_NODEFAULTLIB`가 정의됩니다.  예를 들면 다음과 같습니다.  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **기본 라이브러리 이름 생략** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)