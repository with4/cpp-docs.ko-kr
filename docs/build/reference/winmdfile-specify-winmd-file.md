---
title: "/WINMDFILE(winmd 파일 지정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.GenerateWindowsMetadataFile"
dev_langs: 
  - "C++"
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /WINMDFILE(winmd 파일 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/WINMD](../../build/reference/winmd-generate-windows-metadata.md) 링커 옵션을 사용해서 생성된 Windows 런타임 메타데이터\(winmd\) 출력 파일의 파일 이름을 지정합니다.  
  
```  
  
/WINMDFILE:filename  
  
```  
  
## 설명  
 .winmd 파일 기본 이름 재정의를 하기 위해 \(`binaryname`.winmd\) `filename`  에 지정되어 있는 값을 사용하세요.  ".Winmd"를 추가 하지 마십시오 확인  `filename` .  여러 값에 표시 되는  **\/WINMDFILE**  명령줄 마지막 우선 합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **Windows 메타데이터** 속성 페이지를 선택합니다.  
  
4.  **Windows 메타 데이터 파일**에 상자에 파일 위치를 입력 합니다.  
  
## 참고 항목  
 [\/WINMD\(Windows 메타데이터 생성\)](../../build/reference/winmd-generate-windows-metadata.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)