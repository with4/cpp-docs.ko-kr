---
title: "/WINMD(Windows 메타데이터 생성) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadata"
dev_langs: 
  - "C++"
ms.assetid: bcfb4901-411e-4c9e-9f78-23028b6e5fcc
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMD(Windows 메타데이터 생성)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 런타임 메타데이터 \(.winmd\)파일을 생성할 수 있도록 설정합니다.  
  
```  
  
/WINMD[:{NO|ONLY}]  
```  
  
## 설명  
 \/WINMD  
 기본적으로 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램입니다.  링커가 이진 실행 파일 및.winmd 메타 데이터 파일이 모두 생성 됩니다.  
  
 \/WINMD:NO  
 링커는.winmd 파일이 아니라 하지만 이진 실행 파일을 생성합니다.  
  
 \/WINMD:ONLY  
 링커는.winmd 파일이 아니라 하지만 이진 실행 파일을 생성합니다.  
  
 기본적으로 출력 파일 이름에는  `binaryname` .winmd 형식이 있습니다.  다른 파일 이름을 지정하는 [\/WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md) 옵션입니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **Windows 메타데이터** 속성 페이지를 선택합니다.  
  
4.  **Windows 메타 데이터 서명 생성** 드롭 다운 목록 상자에서 원하는 옵션을 선택 합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)