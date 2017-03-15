---
title: "BSCMAKE 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".bsc 파일, 빌드"
  - "찾아보기 정보 파일(.bsc), 빌드"
  - "창 찾기"
  - "bsc 파일, 빌드"
  - "BSCMAKE"
  - "BSCMAKE, 참조"
  - "Microsoft Browse Information Maintenance Utility"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# BSCMAKE 참조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  BSCMAKE는 Visual Studio와 함께 설치되지만 더 이상 IDE에서 사용되지 않습니다.  Visual Studio 2008부터 찾아보기 및 기호 정보는 자동으로 솔루션 폴더의 SQL Server .sdf 파일에 저장됩니다.  
  
 Microsoft Browse Information Maintenance Utility\(BSCMAKE.EXE\)에서는 컴파일 중에 생성된 .sbr 파일에서 찾아보기 정보 파일\(.bsc\)이 빌드됩니다.  개체 브라우저에서 찾아보기 정보 파일을 볼 수 있습니다.  개체 브라우저에 대한 자세한 내용은 [개체 브라우저에서 탐색](http://msdn.microsoft.com/ko-kr/53eb91aa-08c6-4299-8e3c-a877ae8d0c55)을 참조하세요.  
  
 프로그램을 빌드할 때 BSCMAKE를 사용하여 파일을 빌드하면 프로그램에 대한 찾아보기 정보를 자동으로 만들 수 있습니다.  Visual C\+\+ 개발 환경에서 찾아보기 정보 파일을 만들면 BSCMAKE를 실행하는 방법을 알 필요가 없습니다.  그러나 이 항목을 읽으면 사용 가능한 선택 항목을 이해할 수 있습니다.  
  
 개발 환경 외부에서 프로그램을 빌드하면 해당 환경에서 검사할 수 있는 사용자 지정 .bsc를 만들 수 있습니다.  컴파일 중에 만든 .sbr 파일에서 BSCMAKE를 실행합니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 이 도구를 시작할 수 있습니다.  시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 이 단원에 포함된 항목은 다음과 같습니다.  
  
-   [찾아보기 정보 파일 빌드: 개요](../../build/reference/building-browse-information-files-overview.md)  
  
-   [.bsc 파일 빌드](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [BSCMAKE 명령줄](../../build/reference/bscmake-command-line.md)  
  
-   [BSCMAKE 명령 파일](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [BSCMAKE 옵션](../../build/reference/bscmake-options.md)  
  
-   [BSCMAKE 종료 코드](../../build/reference/bscmake-exit-codes.md)  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)