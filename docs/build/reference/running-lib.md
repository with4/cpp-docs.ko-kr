---
title: "LIB 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.TargetMachine"
  - "Lib"
  - "VC.Project.VCLibrarianTool.PrintProgress"
  - "VC.Project.VCLibrarianTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ 명령 파일"
  - "/MACHINE 대상 플랫폼 옵션"
  - "/NOLOGO 라이브러리 관리자 옵션"
  - "/VERBOSE 라이브러리 관리자 옵션"
  - "콜론 명령 파일"
  - "명령 파일"
  - "명령 파일, LIB"
  - "대시 옵션 지정자"
  - "슬래시 옵션 지정자"
  - "LIB[C++], LIB 실행"
  - "MACHINE 대상 플랫폼 옵션"
  - "-MACHINE 대상 플랫폼 옵션"
  - "NOLOGO 라이브러리 관리자 옵션"
  - "-NOLOGO 라이브러리 관리자 옵션"
  - "세미콜론, 명령 파일"
  - "슬래시(/)"
  - "VERBOSE 라이브러리 관리자 옵션"
  - "-VERBOSE 라이브러리 관리자 옵션"
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LIB 실행
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다양한 명령줄 옵션을 사용하여 LIB를 제어할 수 있습니다.  
  
## LIB 명령줄  
 LIB를 실행하려면 `lib` 명령을 입력한 다음 LIB를 사용하여 수행할 작업에 대한 옵션과 파일 이름을 입력합니다.  LIB에서는 명령 파일에 명령줄을 입력할 수도 있습니다\(자세한 내용은 다음 단원에서 설명\).  또한 LIB에서는 환경 변수를 사용하지 않습니다.  
  
> [!NOTE]
>  Microsoft Windows NT용 Win32 소프트웨어 개발 키트와 함께 제공되는 LINK32.exe 및 LIB32.exe 도구에 익숙한 경우에는 라이브러리를 관리하고 가져오기 라이브러리를 만드는 데 `link32 -lib` 명령이나 `lib32` 명령을 이미 사용하고 있을 수 있습니다.  대신 `lib` 명령을 사용하려면 메이크파일과 배치 파일을 변경해야 합니다.  
  
## LIB 명령 파일  
 명령 파일에서 다음과 같은 구문을 사용하여 LIB에 명령줄 인수를 전달할 수 있습니다.  
  
```  
LIB @commandfile  
```  
  
 `commandfile` 파일은 텍스트 파일입니다.  @ 기호와 파일 이름 사이에는 공백이나 탭을 사용할 수 없습니다.  기본 확장명은 없으며 확장명을 포함한 전체 파일 이름을 사용자가 지정해야 합니다.  와일드카드는 사용할 수 없습니다.  파일 이름과 함께 절대 경로 또는 상대 경로를 지정할 수 있습니다.  
  
 명령 파일에서, 명령줄에 인수가 있을 경우 해당 인수들은 공백이나 탭으로 구분됩니다. 또는 줄 바꿈 문자로 구분될 수도 있습니다.  주석을 표시할 때에는 세미콜론\(;\)을 사용합니다.  LIB는 세미콜론부터 해당 줄의 끝까지 모든 텍스트를 무시합니다.  
  
 명령 파일에서는 명령줄의 전체 또는 일부를 지정할 수 있으며 LIB 명령에 둘 이상의 명령 파일을 사용할 수 있습니다.  LIB는 명령 파일 입력을 마치 명령줄의 해당 위치에서 지정한 것처럼 받아들입니다.  명령 파일을 중첩할 수는 없습니다.  LIB는 \/NOLOGO 옵션이 사용되지 않은 경우 명령 파일의 내용을 에코합니다.  
  
## LIB 옵션 사용  
 옵션은 옵션 지정자\(대시\( \- \) 또는 슬래시\( \/ \) 중 하나\)와 그 다음에 나오는 옵션 이름으로 구성됩니다.  옵션 이름은 약식으로 표기할 수 없습니다.  일부 옵션의 경우에는 콜론\(:\) 뒤에 인수를 지정합니다.  옵션 사양에는 공백이나 탭을 사용할 수 없습니다.  한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다.  옵션 이름과 옵션 키워드 또는 파일 이름 인수는 대\/소문자가 구분되지 않지만 인수로 사용되는 식별자는 대\/소문자가 구분됩니다.  LIB는 명령줄 및 명령 파일에 지정된 순서대로 옵션을 처리합니다.  옵션이 서로 다른 인수를 사용하여 반복되는 경우에는 마지막으로 처리되는 옵션이 우선 순위를 가집니다.  
  
 다음 옵션은 LIB의 모든 모드에 적용됩니다.  
  
 \/ERRORREPORT \[NONE &#124; PROMPT &#124; QUEUE &#124; SEND\]  
 런타임에 lib.exe가 실행되지 않으면 \/ERRORREPORT를 사용하여 이러한 내부 오류에 대한 정보를 Microsoft에 전달할 수 있습니다.  
  
 \/ERRORREPORT에 대한 자세한 내용은 [\/errorReport\(내부 컴파일러 오류 보고\)](../../build/reference/errorreport-report-internal-compiler-errors.md)를 참조하십시오.  
  
 \/LTCG  
 링크 타임 코드 생성을 사용하여 라이브러리를 빌드하도록 지정합니다.  자세한 내용은 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)를 참조하십시오.  
  
 \/MACHINE  
 프로그램에 대한 대상 플랫폼을 지정합니다.  대개는 \/MACHINE을 지정할 필요가 없습니다.  LIB는 .obj 파일에서 컴퓨터 종류를 유추합니다.  하지만 일부 경우에는 LIB에서 컴퓨터 종류를 확인하지 못하여 오류 메시지를 표시할 수도 있습니다.  이러한 오류가 발생하는 경우에는 \/MACHINE을 지정합니다.  \/EXTRACT 모드에서는 이 옵션이 확인 전용입니다.  사용 가능한 컴퓨터 종류를 보려면 명령줄에 `lib /?` 라고 입력합니다.  
  
 \/NOLOGO  
 LIB 저작권 메시지 및 버전 번호가 표시되지 않도록 하고 명령 파일이 에코되지 않도록 합니다.  
  
 \/VERBOSE  
 추가하려는 .obj 파일의 이름을 비롯하여 세션 진행에 대한 자세한 정보를 표시합니다.  이 정보는 표준 출력으로 보내지며 파일로 리디렉션될 수 있습니다.  
  
 \/WX\[:NO\]  
 경고를 오류로 처리합니다.  자세한 내용은 [\/WX\(링커 경고를 오류로 처리\)](../../build/reference/wx-treat-linker-warnings-as-errors.md)를 참조하십시오.  
  
 다른 옵션은 LIB의 특정 모드에만 적용됩니다.  이 옵션들은 각 모드에 대한 설명 단원에서 자세히 설명합니다.  
  
## 참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)