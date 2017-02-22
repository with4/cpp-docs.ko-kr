---
title: "/VERBOSE(진행 메시지 표시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/verbose"
  - "VC.Project.VCLinkerTool.ShowProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERBOSE 링커 옵션"
  - "종속성[C++], 링커 출력의 종속성 정보"
  - "링커[C++], 출력 종속성 정보"
  - "링크[C++], 세션 진행률 정보"
  - "인쇄 진행 메시지 링커 옵션"
  - "VERBOSE 링커 옵션"
  - "-VERBOSE 링커 옵션"
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /VERBOSE(진행 메시지 표시)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## 설명  
 링커에서는 링크 세션의 진행에 대한 정보를 **출력** 창으로 보냅니다.  명령줄에서 이 정보는 표준 출력으로 보내지며 파일로 리디렉션될 수 있습니다.  
  
|옵션|설명|  
|--------|--------|  
|\/VERBOSE|링크 진행 과정을 자세하게 표시합니다.|  
|\/VERBOSE:ICF|[\/OPT:ICF](../../build/reference/opt-optimizations.md)를 사용하여 발생하는 링커 작업에 대한 정보를 표시합니다.|  
|\/VERBOSE:INCR|증분 링크 프로세스에 대한 정보를 표시 합니다.|  
|\/VERBOSE:LIB|검색된 라이브러리만 나타내는 진행 메시지를 표시합니다.<br /><br /> 표시되는 정보에는 라이브러리 검색 프로세스가 포함되며, 각 라이브러리 및 개체 이름 목록\(전체 경로 포함\)과, 라이브러리에서 확인되는 기호, 그리고 기호를 참조하는 개체 목록도 표시됩니다.|  
|\/VERBOSE:REF|[\/OPT:ICF](../../build/reference/opt-optimizations.md)를 사용하여 발생하는 링커 작업에 대한 정보를 표시합니다.|  
|\/VERBOSE:SAFESEH|[\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) 가 지정되지 않은 경우, 안전한 예외 처리와 호환되지 않는 모듈에 대한 정보를 표시합니다.|  
|\/ 자세한: UNUSEDLIBS|이미지를 만들 때 사용하지 않은 라이브러리 파일에 대한 정보를 표시 합니다.|  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)