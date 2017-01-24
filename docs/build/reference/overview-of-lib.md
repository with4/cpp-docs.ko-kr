---
title: "LIB 개요 | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIB[C++], 모드"
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIB 개요
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB는 프로그램을 빌드할 때 [링크](../../build/reference/linker-options.md)와 함께 사용할 수 있는 표준 라이브러리, 가져오기 라이브러리 및 내보내기 파일을 만듭니다.  LIB는 명령 프롬프트에서 실행됩니다.  
  
 LIB는 다음과 같은 모드에서 사용할 수 있습니다.  
  
-   [COFF 라이브러리 빌드 및 변경](../../build/reference/managing-a-library.md)  
  
-   [파일에 멤버 개체 추출](../../build/reference/extracting-a-library-member.md)  
  
-   [가져오기 라이브러리 및 내보내기 파일 만들기](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 이 모드들은 함께 사용할 수 없으며 한 번에 하나의 모드에서만 LIB를 사용할 수 있습니다.  
  
## LIB 옵션  
 다음 표에서는 추가 정보를 볼 수 있는 링크와 함께 lib.exe의 옵션을 보여 줍니다.  
  
 **\/DEF**  
 가져오기 라이브러리 및 내보내기 파일을 만듭니다.  
  
 자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)를 참조하십시오.  
  
 **\/ERRORREPORT**  
 lib.exe의 내부 오류에 대한 정보를 Microsoft에 전송합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
 **\/EXPORT**  
 프로그램에서 함수를 내보냅니다.  
  
 자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)를 참조하십시오.  
  
 **\/EXTRACT**  
 기존 라이브러리의 멤버 복사본이 들어 있는 개체 파일\(.obj\)을 만듭니다.  
  
 자세한 내용은 [라이브러리 멤버 추출](../../build/reference/extracting-a-library-member.md)를 참조하십시오.  
  
 **\/INCLUDE**  
 기호 테이블에 기호를 추가합니다.  
  
 자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)를 참조하십시오.  
  
 **\/LIBPATH**  
 환경 라이브러리 경로를 재정의합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/LIST**  
 출력 라이브러리에 대한 정보를 표준 출력에 표시합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/LTCG**  
 링크 타임 코드 생성을 사용하여 라이브러리를 빌드하도록 지정합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
 **\/MACHINE**  
 프로그램에 대한 대상 플랫폼을 지정합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
 **\/NAME**  
 가져오기 라이브러리를 빌드할 때 사용할 DLL의 이름을 지정합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/NODEFAULTLIB**  
 외부 참조 확인 시 검색한 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/NOLOGO**  
 LIB 저작권 메시지 및 버전 번호가 표시되지 않도록 하고 명령 파일이 에코되지 않도록 합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
 **\/OUT**  
 기본 출력 파일 이름을 재정의합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/REMOVE**  
 출력 라이브러리에서 개체를 제거합니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/SUBSYSTEM**  
 출력 라이브러리에 링크하여 만든 프로그램의 실행 방법을 운영 체제에 알립니다.  
  
 자세한 내용은 [라이브러리 관리](../../build/reference/managing-a-library.md)를 참조하십시오.  
  
 **\/VERBOSE**  
 추가하려는 .obj 파일의 이름을 비롯하여 세션 진행에 대한 자세한 정보를 표시합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
 **\/WX**  
 경고를 오류로 처리합니다.  
  
 자세한 내용은 [LIB 실행](../../build/reference/running-lib.md)를 참조하십시오.  
  
## 참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)   
 [LIB 입력 파일](../../build/reference/lib-input-files.md)   
 [LIB 출력 파일](../../build/reference/lib-output-files.md)   
 [기타 LIB 출력](../../build/reference/other-lib-output.md)   
 [라이브러리 구조](../../build/reference/structure-of-a-library.md)