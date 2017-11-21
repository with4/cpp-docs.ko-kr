---
title: "LIB 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6ea2a91e50bab33ab46f96d63cdc0c1c1023c6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="overview-of-lib"></a>LIB 개요
LIB에서 만드는 표준 라이브러리, 라이브러리, 가져오기 및 내보내기 파일을 사용할 수 있습니다 [링크](../../build/reference/linker-options.md) 는 프로그램을 빌드할 경우. LIB 명령 프롬프트에서 실행 됩니다.  
  
 LIB 다음 모드에서 사용할 수 있습니다.  
  
-   [빌드 또는 COFF 라이브러리 수정](../../build/reference/managing-a-library.md)  
  
-   [멤버 개체를 파일에 추출합니다.](../../build/reference/extracting-a-library-member.md)  
  
-   [가져오기 라이브러리 및 내보내기 파일 만들기](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 이러한 모드는 함께 사용할 수 없습니다. LIB를 한 번에 하나의 모드 에서만 사용할 수 있습니다.  
  
## <a name="lib-options"></a>Lib 옵션  
 다음 표에서에 대 한 자세한 내용은 링크와 함께 lib.exe 옵션을 나열 합니다.  
  
 **/DEF**  
 가져오기 라이브러리 및 내보내기 파일을 만듭니다.  
  
 자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)합니다.  
  
 **/ERRORREPORT**  
 Lib.exe 사용 하 여 내부 오류에 대 한 Microsoft에 정보를 보냅니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
 **/ 내보내기**  
 프로그램에서 함수를 내보냅니다.  
  
 자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)합니다.  
  
 **/ 추출**  
 기존 라이브러리의 멤버의 복사본이 포함 된 개체 (.obj) 파일을 만듭니다.  
  
 자세한 내용은 참조 [라이브러리 멤버 추출](../../build/reference/extracting-a-library-member.md)합니다.  
  
 **/ 포함**  
 기호 테이블에는 기호를 추가합니다.  
  
 자세한 내용은 참조 [가져오기 라이브러리 및 내보내기 파일 빌드](../../build/reference/building-an-import-library-and-export-file.md)합니다.  
  
 **/LIBPATH**  
 환경 라이브러리 경로를 재정의합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/ 목록**  
 표준 출력에 출력 라이브러리에 대 한 정보를 표시합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/LTCG**  
 링크 타임 코드 생성을 사용 하 여 빌드할 라이브러리를 하면 됩니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
 **/ 컴퓨터**  
 프로그램에 대 한 대상 플랫폼을 지정합니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
 **/ 이름**  
 가져오기 라이브러리를 빌드할 때에 작성 중인 가져오기 라이브러리 DLL의 이름을 지정 합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/NODEFAULTLIB**  
 외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거 합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/NOLOGO**  
 LIB 저작권 메시지와 버전 번호가 표시 되지 않도록 하 고 명령 파일의 에코 방지 합니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
 **/ 입 출력**  
 기본 출력 파일 이름을 재정의합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/ 제거**  
 출력 라이브러리에서 개체를 제거 합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/ 하위 시스템**  
 운영 체제를 출력 라이브러리에 연결 하 여 만든 프로그램을 실행 하는 방법을 설명 합니다.  
  
 자세한 내용은 참조 [라이브러리 관리](../../build/reference/managing-a-library.md)합니다.  
  
 **/ 자세한 정보**  
 추가 하려는.obj 파일의 이름을 포함 하 여 세션의 진행률에 대 한 세부 정보를 표시 합니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
 **/WX**  
 경고를 오류로 처리 합니다.  
  
 자세한 내용은 참조 [LIB 실행](../../build/reference/running-lib.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)   
 [LIB 입력된 파일](../../build/reference/lib-input-files.md)   
 [LIB 출력 파일](../../build/reference/lib-output-files.md)   
 [기타 LIB 출력](../../build/reference/other-lib-output.md)   
 [라이브러리 구조](../../build/reference/structure-of-a-library.md)