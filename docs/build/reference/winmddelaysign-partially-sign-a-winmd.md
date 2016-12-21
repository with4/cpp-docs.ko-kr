---
title: "/WINMDDELAYSIGN(winmd에 부분적으로 서명) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.WINMDDelaySign"
dev_langs: 
  - "C++"
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMDDELAYSIGN(winmd에 부분적으로 서명)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일에 공개 키를 삽입 하 여 Windows 런타임 메타 데이터 \(.winmd\) 파일의 일부 서명이 사용 됩니다.  
  
```  
  
/WINMDDELAYSIGN[:NO]  
  
```  
  
## 설명  
 [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md) .winmd 파일에 적용 되는 링커 옵션과 유사합니다.  어셈블리에 .winmd 공개 키만 포함하려면 **\/WINMDDELAYSIGN**를 사용합니다.  기본적으로 링커는 역할 처럼 **\/WINMDDELAYSIGN:NO** 에 지정 했습니다. 즉, winmd 파일을 서명 하지 않습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **Windows 메타데이터** 속성 페이지를 선택합니다.  
  
4.  **Windows 메타 데이터 서명 연기** 드롭 다운 목록 상자에서 원하는 옵션을 선택 합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)