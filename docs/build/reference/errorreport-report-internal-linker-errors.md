---
title: "/ERRORREPORT(내부 링커 오류 보고) | Microsoft Docs"
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
  - "/ERRORREPORT"
  - "VC.Project.VCLinkerTool.ErrorReporting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ERRORREPORT 링커 옵션"
  - "ERRORREPORT 링커 옵션"
  - "-ERRORREPORT 링커 옵션"
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ERRORREPORT(내부 링커 오류 보고)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## 설명  
 ICE\(내부 컴파일러 오류\) 정보를 Microsoft에 직접 제공할 수 있습니다.  
  
 옵션 **\/errorReport:send**는 오류 정보를 Microsoft에 자동으로 보내려고 시도하지만 성공 여부는 레지스트리 설정에 따라 다릅니다.  레지스트리에 적절한 값을 설정하는 더 많은 방법은, MSDN 웹 사이트의 [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command\-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) 를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **구성 속성** 폴더를 클릭합니다.  
  
3.  **링커** 폴더를 클릭합니다.  
  
4.  **고급** 속성 페이지를 클릭합니다.  
  
5.  **오류 보고** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>를 참조하십시오.  
  
## 참고 항목  
 [\/errorReport\(내부 컴파일러 오류 보고\)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)