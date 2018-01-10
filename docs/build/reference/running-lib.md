---
title: "LIB 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
dev_langs: C++
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a487bb6f6ffd740f6479916c5115bf95d568655
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="running-lib"></a>LIB 실행
제어 LIB에 다양 한 명령줄 옵션을 사용할 수 있습니다.  
  
## <a name="lib-command-line"></a>LIB 명령줄  
 LIB를 실행 하려면 명령을 입력 `lib` 된 옵션 및 작업에 대 한 파일 이름을 사용 하 여 LIB 수행 합니다. 또한 LIB 다음 섹션에서 설명 하는 명령 파일에 명령줄 입력을 허용 합니다. LIB 환경 변수를 사용 하지 않습니다.  
  
> [!NOTE]
>  LINK32.exe에 익숙한 및 LIB32.exe 도구와 Microsoft Win32 소프트웨어 개발 키트에 대 한 Windows NT, 있습니다 사용 된 명령 중 하나 제공 하는 경우 `link32 -lib` 또는 명령의 `lib32` 라이브러리를 관리 하 고 만들기 위한 가져오기 라이브러리입니다. 사용 하려면 메이크파일 배치 파일을 변경 하는 `lib` 명령을 사용 합니다.  
  
## <a name="lib-command-files"></a>LIB 명령 파일  
 다음 구문을 사용 하 여 명령 파일의 LIB에 명령줄 인수를 전달할 수 있습니다.  
  
```  
LIB @commandfile  
```  
  
 파일 `commandfile` 텍스트 파일입니다. 없음 공백 또는 탭 간 허용 되는 at 기호 (@) 및 파일 이름입니다. 기본 확장명이 없습니다. 모든 확장을 포함 하 여 전체 파일 이름을 지정 해야 합니다. 와일드 카드를 사용할 수 없습니다. 파일 이름으로 절대 또는 상대 경로 지정할 수 있습니다.  
  
 명령 파일의 인수도 구분할 수 있습니다 공백이 나 탭; 명령줄에서 수 또한 줄 바꿈 문자로 구분 수 있습니다. 세미콜론 (;)를 사용 하 여 주석을 표시 합니다. LIB 줄의 끝에 세미콜론에서 모든 텍스트를 무시합니다.  
  
 명령 파일의 전체 또는 명령줄의 일부를 지정할 수 있습니다 및 LIB 명령에 명령 파일을 여러 개 사용할 수 있습니다. LIB은 명령줄에서 해당 위치에 지정 된 것 처럼 명령 파일 입력을 받아들입니다. 명령 파일을 중첩할 수 없습니다. LIB에 /NOLOGO 옵션을 사용 하지 않으면 명령 파일의 내용을 표시 합니다.  
  
## <a name="using-lib-options"></a>LIB 옵션을 사용 하 여  
 옵션은 옵션 지정자는 대시 (-) 또는 슬래시 (/) 옵션의 이름이 차례로 나옵니다 구성 됩니다. 옵션 이름은 축약 될 수 없습니다. 일부 옵션이 콜론 (:) 다음에 지정 된 인수를 사용 합니다. 공백 또는 탭 옵션 사양에 허용 됩니다. 하나 이상의 공백이 나 탭을 사용 하 여 명령줄에서 옵션 사양을 구분 합니다. 옵션 이름 및 키워드 또는 파일 이름 인수는 대/소문자를 구분 하지 않는 식별자 인수로 사용 되는 대/소문자 구분. LIB 옵션 명령줄에 지정 된 순서로 및 명령 파일을 처리 합니다. 옵션은 반복 경우 서로 다른 인수를 사용, 마지막 트랜잭션이 처리 되도록 우선 합니다.  
  
 다음 옵션의 LIB 모든 모드에 적용 됩니다.  
  
 /ERRORREPORT [없음 &#124; 프롬프트 &#124; QUEUE&#124; 송신]  
 런타임에 lib.exe 실패 하면 이러한 내부 오류에 대 한 정보를 Microsoft로 보내도록 /ERRORREPORT를 사용할 수 있습니다.  
  
 /ERRORREPORT에 대 한 자세한 내용은 참조 [/errorReport (내부 컴파일러 오류 보고)](../../build/reference/errorreport-report-internal-compiler-errors.md)합니다.  
  
 /LTCG  
 링크 타임 코드 생성을 사용 하 여 빌드할 라이브러리를 하면 됩니다.  자세한 내용은 참조 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)합니다.  
  
 /MACHINE  
 프로그램에 대 한 대상 플랫폼을 지정합니다. 일반적으로 /MACHINE 지정할 필요가 없습니다. LIB은.obj 파일에서 컴퓨터 종류를 유추합니다. 그러나 경우에 따라 LIB 컴퓨터 유형을 확인할 수 없습니다 및 오류 메시지입니다. 이러한 오류가 발생 하는 경우 /MACHINE를 지정 합니다. /EXTRACT 모드에서이 옵션은 확인만 됩니다. 사용 하 여 `lib /?` 에서 명령줄을 입력 합니다.  
  
 /NOLOGO  
 LIB 저작권 메시지와 버전 번호가 표시 되지 않도록 하 고 명령 파일의 에코 방지 합니다.  
  
 /VERBOSE  
 추가 하려는.obj 파일의 이름을 포함 하 여 세션의 진행률에 대 한 세부 정보를 표시 합니다. 이 정보는 표준 출력으로 보내지며 파일로 리디렉션될 수 있습니다.  
  
 /WX [: NO]  
 경고를 오류로 처리 합니다. 참조 [/WX (링커 경고를 오류로 처리)](../../build/reference/wx-treat-linker-warnings-as-errors.md) 자세한 정보에 대 한 합니다.  
  
 다른 옵션의 LIB 특정 모드에만 적용 됩니다. 이러한 옵션은 각 모드를 설명 하는 섹션에 설명 되어 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)