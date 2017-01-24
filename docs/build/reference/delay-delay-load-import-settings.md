---
title: "/DELAY(가져오기 설정 로드 지연) | Microsoft Docs"
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
  - "/delay"
  - "VC.Project.VCLinkerTool.DelayNoBind"
  - "VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL"
  - "VC.Project.VCLinkerTool.DelayUnload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY 링커 옵션"
  - "DELAY 링커 옵션"
  - "-DELAY 링커 옵션"
  - "지연 DLL 로드, /DELAY 옵션"
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAY(가져오기 설정 로드 지연)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## 설명  
 \/DELAY 옵션은 다음과 같이 DLL의 [지연 로드](../../build/reference/linker-support-for-delay-loaded-dlls.md)를 제어합니다.  
  
-   UNLOAD 한정자는 지연 로드 도우미 함수에 DLL의 명시적 언로드를 지원하도록 지시합니다.  IAT\(가져오기 주소 테이블\)는 원래 폼으로 다시 설정되어 IAT 포인터를 무효화하고 해당 포인터를 덮어쓰게 합니다.  
  
     UNLOAD를 선택하지 않으면 [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)에 대한 모든 호출이 실패합니다.  
  
-   NOBIND 한정자는 링커에 바인딩할 수 있는 IAT를 최종 이미지에서 제외하도록 지시합니다.  기본값은 지연 로드된 DLL에 대해 바인딩할 수 있는 IAT를 만드는 것입니다.  결과 이미지는 정적으로 바인딩할 수 없습니다.  바인딩할 수 있는 IAT가 포함된 이미지는 실행 전에 정적으로 바인딩할 수 없습니다. [\/BIND](../../build/reference/bind.md)를 참조하세요.  
  
     DLL이 바인딩되면 도우미 함수는 참조된 각 가져오기 시 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)를 호출하는 대신 바인딩 정보를 사용하려고 합니다.  타임스탬프 또는 기본 설정 주소가 로드된 DLL의 타임스탬프 또는 기본 설정 주소와 일치하지 않으면 도우미 함수는 바인딩된 IAT가 오래되었다고 가정하고 마치 바인딩된 IAT가 없는 것처럼 진행합니다.  
  
     NOBIND는 프로그램 이미지를 더 크게 만들지만 DLL 로드 시간은 단축할 수 있습니다.  DLL 바인딩을 의도하지 않은 경우 NOBIND는 바인딩된 IAT가 생성되지 않도록 합니다.  
  
 지연 로드될 DLL을 지정하려면 [\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) 옵션을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **구성 속성**, **링커**를 확장하고 **고급**을 선택합니다.  
  
3.  **지연 로드된 DLL** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)