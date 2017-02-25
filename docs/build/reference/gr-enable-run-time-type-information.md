---
title: "/GR(런타임 형식 정보 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/gr"
  - "VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo"
  - "VC.Project.VCCLCompilerTool.RuntimeTypeInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gr 컴파일러 옵션[C++]"
  - "런타임 형식 정보 사용 컴파일러 옵션[C++]"
  - "Gr 컴파일러 옵션[C++]"
  - "-Gr 컴파일러 옵션[C++]"
  - "RTTI 컴파일러 옵션"
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /GR(런타임 형식 정보 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

런타임에 개체 형식을 검사하는 코드를 추가합니다.  
  
## 구문  
  
```  
/GR[-]  
```  
  
## 설명  
 **\/GR**를 사용하면 컴파일러는 `_CPPRTTI` 전처리기 매크로를 정의합니다.  **\/GR**는 기본적으로 사용됩니다.  **\/GR\-**을 사용하면 런타임 형식 정보를 비활성화할 수 있습니다.  
  
 코드의 개체 형식을 컴파일러에서 정적으로 확인할 수 없는 경우 **\/GR**을 사용합니다.  일반적으로 코드에서 [dynamic\_cast 연산자](../../cpp/dynamic-cast-operator.md) 또는 [typeid](../../cpp/typeid-operator.md)를 사용할 경우 **\/GR** 옵션이 필요합니다.  그러나 **\/GR**을 사용하면 이미지의 .rdata 섹션 크기가 증가합니다.  코드에서 **dynamic\_cast** 또는 **typeid**를 사용하지 않는 경우 **\/GR\-**을 사용하여 이미지 크기를 줄일 수 있습니다.  
  
 런타임 형식 검사에 대한 자세한 내용은 *C\+\+ 언어 참조*에서 [런타임 형식 정보](../../cpp/run-time-type-information.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **언어** 속성 페이지를 클릭합니다.  
  
4.  **런타임 형식 정보 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)