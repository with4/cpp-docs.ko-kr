---
title: "/FORCE(파일 출력 강제) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.ForceLink"
  - "/force"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FORCE 링커 옵션"
  - "링커의 파일 출력"
  - "FORCE 링커 옵션"
  - "-FORCE 링커 옵션"
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FORCE(파일 출력 강제)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## 설명  
 \/FORCE 옵션을 사용하면 링커에서는 기호가 참조되어 있지만 정의되어 있지 않은 경우나 여러 번 정의되어 있는 경우에도 올바른 .exe 파일 또는 DLL을 만듭니다.  
  
 \/FORCE 옵션에는 다음과 같이 선택적 인수를 사용할 수 있습니다.  
  
-   \/FORCE:MULTIPLE을 사용하면 LINK에서 한 기호에 대해 두 개 이상의 정의를 찾은 경우에도 출력 파일을 만듭니다.  
  
-   \/FORCE:UNRESOLVED를 사용하면 LINK가 정의되지 않은 기호를 찾은 경우에도 출력 파일을 만듭니다. 진입점 기호를 확인하지 못한 경우에는 \/FORCE:UNRESOLVED가 무시됩니다.  
  
 인수 없이 \/FORCE를 사용하면 multiple과 unresolved가 모두 지정된 것으로 처리됩니다.  
  
 이 옵션을 사용하여 만든 파일이 예상대로 실행되지 않을 수도 있습니다.  링커에서는 \/FORCE 옵션이 지정된 경우 증분 링크를 수행하지 않기 때문입니다.  
  
 **\/clr**를 사용하여 모듈을 컴파일하는 경우 **\/FORCE**를 지정해도 이미지가 생성되지 않습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)