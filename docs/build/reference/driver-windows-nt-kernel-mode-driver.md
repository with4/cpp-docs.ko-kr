---
title: "/DRIVER(Windows NT 커널 모드 드라이버) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.driver"
  - "/driver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DRIVER 링커 옵션"
  - "DRIVER 링커 옵션"
  - "-DRIVER 링커 옵션"
  - "커널 모드 드라이버"
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DRIVER(Windows NT 커널 모드 드라이버)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DRIVER[:UPONLY | :WDM]  
```  
  
## 설명  
 \/DRIVER 링커 옵션을 사용하면 Windows NT 커널 모드 드라이버를 빌드할 수 있습니다.  
  
 **\/DRIVER:UPONLY**를 사용하면 링커에서는 출력 헤더의 특성에 **IMAGE\_FILE\_UP\_SYSTEM\_ONLY** 비트를 추가하여 해당 출력 헤더를 UP\(단일 프로세서\) 드라이버로 지정합니다.  MP\(다중 프로세서\) 시스템의 운영 체제에서는 UP 드라이버를 로드하지 않습니다.  
  
 **\/DRIVER:WDM**을 사용하면 링커에서는 선택적 헤더의 DllCharacteristics 필드에 **IMAGE\_DLLCHARACTERISTICS\_WDM\_DRIVER** 비트를 설정합니다.  
  
 **\/DRIVER**를 지정하지 않는 경우 이러한 비트는 링커에서 설정되지 않습니다.  
  
 **\/DRIVER**를 지정하는 경우  
  
-   \/FIXED:NO가 적용됩니다\([\/FIXED\(고정 기준 주소\)](../../build/reference/fixed-fixed-base-address.md)\).  
  
-   출력 파일의 확장명은 .sys가 됩니다.  기본 파일 이름과 확장명\([\/OUT\(출력 파일 이름\)](../../build/reference/out-output-file-name.md)\)을 변경하려면 **\/OUT**을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **시스템** 속성 페이지를 클릭합니다.  
  
4.  **드라이버** 속성을 변경합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  `P:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.driver`를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)