---
title: "/favor(아키텍처에 맞게 최적화) | Microsoft Docs"
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
  - "/favor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-favor 컴파일러 옵션[C++]"
  - "/favor 컴파일러 옵션[C++]"
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
caps.latest.revision: 31
caps.handback.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /favor(아키텍처에 맞게 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

AMD64와 EM64T 모두에서 특정 마이크로 아키텍처에 맞게 최적화되거나 특정 **\/favor:**`option` 아키텍처에 맞게 최적화된 코드를 생성합니다.  
  
## 구문  
  
```  
/favor:{blend | ATOM | AMD64 | INTEL64}  
```  
  
## 설명  
 **\/favor:blend**  
 \(x86 and x64\) 는 AMD 및 Intel64 아키텍처 모두의 마이크로 아키텍처 특징에 맞게 최적화된 코드를 생성합니다.  **\/favor:blend**는 특정 프로세서에 대해 최고 성능을 제공하지 못할 수도 있으나 x86과 x64프로세서에서 최상의 성능을 제공하도록 설계되었습니다.  기본적으로, **\/favor:blend**가 설정되어 있습니다.  
  
 **\/favor:ATOM**  
 \(x86 및 x64\)는 인텔 아톰 프로세서와 인텔 센트리노 아톰 프로세서 기술에 맞게 최적화 된 코드를 생성 합니다.  코드를 사용 하 여 생성 되는  **\/favor:ATOM**  인텔 프로세서용 인텔 SSSE3, SSE3 SSE2 및 SSE 지침을 만들 수 있습니다.  
  
 **\/favor:AMD64**  
 \(x64만\)는 생성된 코드를 64비트 확장을 지원하는 AMD Opteron 및 Athlon 프로세서에 맞게 최적화합니다.  최적화된 코드는 모든 x64 호환 플랫폼에서 실행할 수 있습니다.  **\/favor:AMD64**를 사용하여 생성된 코드는 Intel64를 지원하는 Intel 프로세서의 성능을 저하시킬 수도 있습니다.  
  
 **\/favor:INTEL64**  
 \(x64만\)눈 컴파일러에서만 사용할 수 있으며 생성된 코드를 Intel64를 지원하는 Intel 프로세서에 맞게 최적화하여 이러한 플랫폼의 성능을 향상시킵니다.  결과 코드는 모든 x64 플랫폼에서 실행할 수 있습니다.  **\/favor:INTEL64**를 사용하여 생성된 코드의 경우 64비트 확장을 지원하는 AMD Opteron 및 Athlon 프로세서에서는 성능이 더 저하될 수 있습니다.  
  
> [!NOTE]
>  Intel64 아키텍쳐는 EM64T\(Extended Memory 64 Technology\)로 알려져 있으며 관련된 컴파일 옵션은 **\/favor:EM64T**입니다.  
  
 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]아키텍처를 위한 [x64 소프트웨어 규칙](../../build/x64-software-conventions.md) 프로그래밍에 대한 자세한 내용은 을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)