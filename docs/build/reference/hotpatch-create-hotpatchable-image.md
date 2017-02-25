---
title: "/hotpatch(핫 패치 가능 이미지 만들기) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/hotpatch"
  - "VC.Project.VCCLCompilerTool.CreateHotpatchableImage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "핫 패치"
  - "-hotpatch 컴파일러 옵션[C++]"
  - "/hotpatch 컴파일러 옵션[C++]"
  - "핫 패치"
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# /hotpatch(핫 패치 가능 이미지 만들기)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

핫 패치를 위해 이미지를 준비합니다.  
  
## 구문  
  
```  
/hotpatch  
```  
  
## 설명  
 컴파일에 **\/hotpatch**를 사용하는 경우, 컴파일러에서는 핫 패치에 필요한 대로 각 함수의 첫 번째 명령이 2바이트가 되도록 합니다.  
  
 사용 후 핫 패치할 수 있는 이미지를 만들기 위한 준비를 완료 하려면  **\/hotpatch**  를 컴파일하는 데 사용 하여 [\/FUNCTIONPADMIN\(핫 패치 가능 이미지 만들기\)](../../build/reference/functionpadmin-create-hotpatchable-image.md) 연결 합니다.  cl.exe를 한 번 실행하여 이미지를 컴파일하고 링크하는 경우, **\/hotpatch**를 사용하면 **\/functionpadmin**이 자동으로 적용됩니다.  
  
 지시는 항상 2 바이트 이상이 ARM 아키텍처에 때문에 x64 컴파일에 항상 처리 처럼  **\/hotpatch**  지정한 지정할 필요가 없습니다  **\/hotpatch**  ; 이러한 대상에 대 한 컴파일할 때 하지만 사용 하 여 계속 연결 해야  **\/functionpadmin**  핫 패치할 수 있는 이미지를 만들 수 있습니다.   **\/hotpatch**  x86 영향 컴파일 전용 컴파일러 옵션입니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 지침  
 업데이트 관리에 대한 자세한 내용은 ["업데이트 관리에 대 한 보안 지침"](http://www.microsoft.com/technet/security/guidance/PatchManagement.mspx)을 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)