---
title: "/FIXED(고정 기준 주소) | Microsoft Docs"
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
  - "/fixed"
  - "VC.Project.VCLinkerTool.FixedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FIXED 링커 옵션"
  - "FIXED 링커 옵션"
  - "-FIXED 링커 옵션"
  - "프로그램을 로드하기 위한 기본 설정 기준 주소"
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FIXED(고정 기준 주소)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FIXED[:NO]  
```  
  
## 설명  
 운영 체제에게 기본 설정 기준 주소에서만 프로그램을 로드하도록 합니다.  기본 설정 기준 주소를 사용할 수 없으면 파일이 로드되지 않습니다.  자세한 내용은 [\/BASE\(기준 주소\)](../../build/reference/base-base-address.md)을 참조하십시오.  
  
 \/FIXED:NO 는 DLL에 대한 기본 설정값이며 \/FIXED는 다른 모든 프로젝트 형식에 대한 기본 설정값입니다.  
  
 \/FIXED를 지정하면 LINK에서는 프로그램에 재배치 섹션을 생성하지 않습니다.  런타임에서 운영 체제가 지정된 주소에서 프로그램을 로드할 수 없으면 오류 메시지가 표시되며 프로그램은 로드되지 않습니다.  
  
 프로그램에 재배치 섹션을 생성하려면 \/FIXED:NO를 지정합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 상자에서 옵션 이름을 입력하고 설정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)