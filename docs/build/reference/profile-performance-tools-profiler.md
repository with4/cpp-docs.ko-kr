---
title: "/PROFILE(성능 도구 프로파일러) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.Profile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PROFILE 링커 옵션"
  - "-PROFILE 링커 옵션"
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /PROFILE(성능 도구 프로파일러)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

성능 도구 프로파일러에서 사용할 수 있는 출력 파일을 생성합니다.  
  
## 구문  
  
```  
/PROFILE  
```  
  
## 설명  
 \/PROFILE은 다음과 같은 링커 옵션을 함축하고 있습니다.  
  
-   [\/OPT:REF](../../build/reference/opt-optimizations.md)  
  
-   \/OPT:NOICF  
  
-   [\/INCREMENTAL:NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [\/FIXED:NO](../../build/reference/fixed-fixed-base-address.md)  
  
 \/PROFILE을 사용하면 링커가 프로그램 이미지에 재배치 섹션을 생성하도록 지시할 수 있습니다.  재배치 섹션을 사용하면 프로파일러가 프로그램 이미지를 변환하여 프로필 데이터를 가져올 수 있습니다.  
  
 **\/PROFILE**은 엔터프라이즈\(팀 개발\) 버전에서만 사용할 수 있습니다.  PREfast에 대한 자세한 내용은 [C\/C\+\+용 코드 분석 개요](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **고급** 속성 페이지를 선택합니다.  
  
5.  **프로필** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)