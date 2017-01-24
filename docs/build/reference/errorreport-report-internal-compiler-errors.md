---
title: "/errorReport(내부 컴파일러 오류 보고) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.ErrorReporting"
  - "/errorreport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/errorReport 컴파일러 옵션[C++]"
  - "-errorReport 컴파일러 옵션[C++]"
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /errorReport(내부 컴파일러 오류 보고)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ICE\(내부 컴파일러 오류\) 정보를 Microsoft에 직접 제공할 수 있습니다.  
  
## 구문  
  
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## 인수  
 **none**  
 내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.  
  
 **prompt**  
 내부 컴파일러 오류가 발생하면 보고서를 보내는 메시지를 표시합니다.  **prompt**는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.  
  
 **queue**  
 오류 보고서를 대기시킵니다.  관리자 권한으로 로그인하면 마지막으로 로그인한 이후 발생한 모든 오류를 보고할 수 있는 창이 표시됩니다. 오류 보고서를 전송할지 확인하는 메시지는 3일에 한 번 이상은 나타나지 않습니다.  **queue**는 명령 프롬프트에서 응용 프로그램을 컴파일할 때 기본값입니다.  
  
 **send**  
 내부 컴파일러 오류 보고서를 자동으로 Microsoft에 보냅니다.  이 옵션을 사용하려면 먼저 Microsoft의 데이터 수집 정책에 동의해야 합니다.  컴퓨터에서 처음으로 **\/errorReport:send**를 지정하면 Microsoft의 데이터 수집 정책이 있는 웹 사이트로 연결되는 컴파일러 메시지가 나타납니다.  
  
 이 옵션은 레지스트리 설정에 따라 달라집니다.  레지스트리에 적절한 값을 설정하는 방법은, MSDN 웹 사이트의 [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command\-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) 를 참조하십시오.  
  
## 설명  
 ICE\(내부 컴파일러 오류\)는 컴파일러에서 소스 코드 파일을 처리할 수 없을 때 발생합니다.  ICE가 발생하면 컴파일러는 코드를 수정하는 데 유용한 진단 정보나 출력 파일을 생성하지 않습니다.  
  
 이전 릴리스에서는 ICE가 발생한 경우 Microsoft 기술 지원 서비스에 연락하여 문제점을 보고하라는 메시지가 표시되었습니다.  **\/errorReport**를 사용하면 Microsoft에 ICE 정보를 직접 제공할 수 있습니다.  오류 보고서는 다음에 릴리스될 컴파일러를 개선하는 데 도움이 됩니다.  
  
 사용자가 보고서를 보낼 수 있는지 여부는 컴퓨터 및 사용자 정책 권한에 따라 다릅니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)을 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **오류 보고** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)