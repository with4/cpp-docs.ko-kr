---
title: "프로젝트 빌드 오류 PRJ0003 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0003"
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0003
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'command line'을\(를\) 생성하는 동안 오류가 발생했습니다.  
  
 **속성 페이지** 대화 상자에 입력한 내용을 통해 만들어진 ***command line*** 명령에서 오류 코드를 반환했지만 출력 창에는 내용이 표시되지 않습니다.  
  
 이 오류의 가능한 이유는 다음과 같습니다.  
  
-   프로젝트가 ATL 서버를 기반으로 합니다.  [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]부터 ATL 서버는 더 이상 Visual Studio의 일부로 포함되지 않지만 CodePlex에서 공유 소스 프로젝트로 릴리스되었습니다.  ATL 서버의 소스 코드와 도구를 다운로드 하려면 [http:\/\/go.microsoft.com\/fwlink\/?LinkID\=81979](http://go.microsoft.com/fwlink/?LinkID=81979)로 가십시오.  
  
-   시스템 리소스가 부족합니다.  이 문제를 해결하려면 일부 응용 프로그램을 닫습니다.  
  
-   보안 권한이 충분하지 않습니다.  보안 권한이 충분한지 확인합니다.  
  
-   [VC\+\+ 디렉터리](http://msdn.microsoft.com/ko-kr/e027448b-c811-4c3d-8531-4325ad3f6e02)에 지정된 실행 파일 경로에 실행하려고 하는 도구의 경로가 포함되어 있지 않습니다.  
  
-   메이크파일 프로젝트일 경우 **빌드 명령줄** 또는 **다시 빌드 명령줄**에서 실행할 명령이 없습니다.  
  
## 참고 항목  
 [프로젝트 빌드 오류 및 경고\(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)