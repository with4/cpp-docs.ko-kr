---
title: "/arch(x64) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /arch(x64)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

x64에서 코드 생성 아키텍처를 지정합니다.  [\/arch\(x86\)](../../build/reference/arch-x86.md) 및 [\/arch\(ARM\)](../../build/reference/arch-arm.md)를 참조하세요.  
  
## 구문  
  
```  
/arch:[AVX|AVX2]  
```  
  
## 인수  
 **\/arch:AVX**  
 Intel Advanced Vector Extensions 명령을 사용하도록 설정합니다.  
  
 **\/arch:AVX2**  
 Intel 고급 벡터 확장 2 명령을 사용하도록 설정합니다.  
  
## 설명  
 **\/arch**는 네이티브 함수에 대한 코드 생성에만 영향을 미칩니다.  [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일하는 경우 **\/arch**는 관리되는 함수의 코드 생성에 영향을 주지 않습니다.  
  
 `__AVX__` 전처리기 기호는 **\/arch:AVX** 컴파일러 옵션을 지정한 경우 정의됩니다.  `__AVX2__` 전처리기 기호는 **\/arch:AVX2** 컴파일러 옵션을 지정한 경우 정의됩니다.  자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)를 참조하세요.  **\/arch:AVX2** 옵션은 Visual Studio 2013 업데이트 2 버전 12.0.34567.1에서 도입되었습니다.  
  
### Visual Studio에서 \/arch:AVX 또는 \/arch:AVX2 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **구성 속성**, **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **코드 생성** 속성 페이지를 선택합니다.  
  
4.  **고급 명령 집합 사용** 드롭다운 상자에서 **고급 벡터 확장\(\/arch:AVX\)** 또는 **고급 벡터 확장 2\(\/arch:\/AVX2\)**를 선택합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하세요.  
  
## 참고 항목  
 [\/arch\(최소 CPU 아키텍처\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)