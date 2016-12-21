---
title: "/RELEASE(체크섬 설정) | Microsoft Docs"
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
  - "/release"
  - "VC.Project.VCLinkerTool.SetChecksum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE 링커 옵션"
  - "체크섬 설정"
  - "RELEASE 링커 옵션"
  - "-RELEASE 링커 옵션"
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RELEASE(체크섬 설정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## 설명  
 \/RELEASE 옵션은 .exe 파일의 헤더에 체크섬을 설정합니다.  
  
 운영 체제에는 장치 드라이버에 대한 체크섬이 필요합니다.  이후의 운영 체제와 호환되게 하려면 장치 드라이버의 릴리스 버전에 체크섬을 설정합니다.  
  
 [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) 옵션을 지정하면 \/RELEASE 옵션이 기본적으로 설정됩니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **체크섬 설정** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)