---
title: "/WINMDKEYCONTAINER(키 컨테이너 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.WINMDKEYCONTAINER"
dev_langs: 
  - "C++"
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /WINMDKEYCONTAINER(키 컨테이너 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 메타데이터 \(.winmd\)파일에 서명하는 키 컨테이너를 지정합니다.  
  
```  
  
/WINMDKEYCONTAINER:name  
  
```  
  
## 설명  
 [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) \(.winmd\) 파일에 적용 되는 링커 옵션입니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **Windows 메타데이터** 속성 페이지를 선택합니다.  
  
4.  **Windows 메타 데이터 Key 파일 컨테이너**에 상자에 파일 위치를 입력 합니다.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)