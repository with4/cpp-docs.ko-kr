---
title: "/arch(ARM) | Microsoft Docs"
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
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch(ARM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ARM에서 코드 생성 아키텍처를 지정합니다.  [\/arch\(x86\)](../../build/reference/arch-x86.md) 및 [\/arch\(x64\)](../../build/reference/arch-x64.md)도 참조하십시오.  
  
## 구문  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## 인수  
 **\/arch:ARMv7VE**  
 ARMv7VE 가상화 확장 명령을 사용하도록 설정합니다.  
  
 **\/arch:VFPv4**  
 ARM VFPv4 명령을 사용하도록 설정합니다.  이 옵션을 지정하지 않으면 VFPv3이 기본값입니다.  
  
## 설명  
 `_M_ARM_FP` 매크로\(ARM만 해당\)는 사용된 **\/arch** 컴파일러 옵션\(있는 경우\)을 나타냅니다.  자세한 내용은 [미리 정의된 매크로](../../preprocessor/predefined-macros.md)을 참조하십시오.  
  
 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일하는 경우 **\/arch**는 관리되는 함수의 코드 생성에 영향을 주지 않습니다.  **\/arch**는 네이티브 함수에 대한 코드 생성에만 영향을 미칩니다.  
  
### Visual Studio에서 \/arch:ARMv7VE 또는 \/arch:VFPv4 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 `/arch:ARMv7VE` 또는 `/arch:VFPv4`를 추가합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>을 참조하십시오.  
  
## 참고 항목  
 [\/arch\(최소 CPU 아키텍처\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)