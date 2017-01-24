---
title: "/INCREMENTAL(증분 링크) | Microsoft Docs"
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
  - "/incremental"
  - "VC.Project.VCLinkerTool.LinkIncremental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCREMENTAL 링커 옵션"
  - "INCREMENTAL 링커 옵션"
  - "-INCREMENTAL 링커 옵션"
  - "증분 링크"
  - "증분 링크 옵션"
  - "LINK 도구[C++], 전체 링크 옵션"
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /INCREMENTAL(증분 링크)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCREMENTAL[:NO]  
```  
  
## 설명  
 링커에서 증분 링크를 처리하는 방법을 제어합니다.  
  
 기본적으로 링커는 증분 모드에서 실행됩니다.  기본 증분 링크를 무시하려면 \/INCREMENTAL:NO를 지정합니다.  
  
 증분 링크된 프로그램은 비증분 링크된 프로그램과 기능적으로 동등합니다.  그러나 후속 증분 링크에 대비하기 때문에 증분 링크된 실행 파일\(.exe\)이나 DLL\(동적 연결 라이브러리\)은 다음과 같은 특징을 갖습니다.  
  
-   코드와 데이터를 패딩하기 때문에 비증분 링크된 프로그램보다 크기가 큽니다. 패딩으로 인해 링커에서는 .exe 파일을 다시 만들지 않고도 함수와 데이터의 크기를 늘릴 수 있습니다.  
  
-   함수를 새 주소로 재배치하는 것을 처리하기 위해 점프 썽크를 포함할 수 있습니다.  
  
    > [!NOTE]
    >  최종 릴리스 빌드에 패딩이나 썽크를 포함시키지 않으려면 프로그램을 비증분 링크합니다.  
  
 기본값에 상관없이 증분 링크하려면 \/INCREMENTAL을 지정합니다.  이 옵션을 선택하면 링커에서는 프로그램을 증분 링크할 수 없는 경우 경고를 표시한 다음 비증분 링크합니다.  특정 옵션을 사용하는 때나 특정 경우에는 \/INCREMENTAL이 무시됩니다.  
  
 대부분의 프로그램은 증분 링크될 수 있습니다.  그러나 일부 변경 사항이 너무 크면 일부 옵션이 증분 링크와 호환되지 않습니다.  LINK에서는 다음 옵션 중 하나가 지정되어 있으면 전체 링크를 수행합니다.  
  
-   증분 링크를 선택하지 않은 경우\(\/INCREMENTAL:NO\)  
  
-   \/OPT:REF를 선택한 경우  
  
-   \/OPT:ICF를 선택한 경우  
  
-   \/OPT:LBR을 선택한 경우  
  
-   \/ORDER을 선택한 경우  
  
 [\/DEBUG](../../build/reference/debug-generate-debug-info.md)를 지정하면 \/INCREMENTAL도 지정됩니다.  
  
 또한 LINK에서는 다음과 같은 경우에 전체 링크를 수행합니다.  
  
-   증분 상태 파일\(.ilk\)이 없는 경우 이 경우 LINK에서는 후속 증분 링크에 사용할 새 .ilk 파일을 만듭니다.  
  
-   .ilk 파일에 대한 쓰기 권한이 없는 경우. 이 경우 LINK에서는 .ilk를 무시하고 비증분 링크를 수행합니다.  
  
-   .exe 또는 .dll 출력 파일이 없는 경우.  
  
-   .ilk, .exe, .dll의 타임스탬프가 변경된 경우.  
  
-   LINK 옵션이 변경된 경우.  대부분의 LINK 옵션은 각 빌드 간에 변경된 경우 전체 링크를 수행합니다.  
  
-   개체 파일\(.obj\)이 추가되거나 생략된 경우.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **증분 링크 사용** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)