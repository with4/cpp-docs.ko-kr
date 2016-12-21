---
title: "/Zp(구조체 멤버 맞춤) | Microsoft Docs"
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
  - "/zp"
  - "VC.Project.VCCLCompilerTool.StructMemberAlignment"
  - "VC.Project.VCCLWCECompilerTool.StructMemberAlignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zp 컴파일러 옵션[C++]"
  - "구조체 멤버 맞춤 컴파일러 옵션"
  - "Zp 컴파일러 옵션"
  - "-Zp 컴파일러 옵션[C++]"
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zp(구조체 멤버 맞춤)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구조체의 멤버가 메모리에 압축되는 방식을 제어하고 모듈의 모든 구조체에 대해 동일한 압축을 지정합니다.  
  
## 구문  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## 설명  
 이 옵션을 지정하면 첫 번째 멤버 다음의 각 구조체 멤버는 멤버 형식의 크기나 `n`\-바이트 경계\(여기서 `n`은 1, 2, 4, 8 또는 16\) 중 작은 쪽에 저장됩니다.  
  
 다음 표에서는 사용할 수 있는 값을 보여 줍니다.  
  
 1  
 1바이트 경계에서 구조체를 압축합니다.  **\/Zp**와 동일합니다.  
  
 2  
 2바이트 경계에서 구조체를 압축합니다.  
  
 4  
 4바이트 경계에서 구조체를 압축합니다.  
  
 8  
 8바이트 경계에서 구조체를 압축합니다\(기본값\).  
  
 16  
 16바이트 경계에서 구조체를 압축합니다.  
  
 특정 맞춤 요구 사항이 없는 경우에는 이 옵션을 사용하면 안 됩니다.  
  
 또한 [pack](../../preprocessor/pack.md)을 사용하여 구조체 압축을 제어할 수도 있습니다.  정렬에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [맞춤](../../cpp/align-cpp.md)  
  
-   [\_\_alignof 연산자](../../cpp/alignof-operator.md)  
  
-   [\_\_unaligned](../../cpp/unaligned.md)  
  
-   [구조체 맞춤 예제](../../build/examples-of-structure-alignment.md)\(x64용\)  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **코드 생성** 속성 페이지를 클릭합니다.  
  
4.  **구조체 멤버 맞춤** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)