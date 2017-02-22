---
title: "연습: 명령줄에서 C 프로그램 컴파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
helpviewer_keywords: 
  - "C 프로그램 컴파일[C++]"
  - "명령줄 응용 프로그램[C++], C 프로그램"
  - "프로그램 컴파일[C++]"
  - "Visual C, 컴파일"
ms.assetid: 7e74cc2d-54b1-49de-b7ad-d3ae6b39ab8d
caps.latest.revision: 46
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# 연습: 명령줄에서 C 프로그램 컴파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에는 기본적인 콘솔 프로그램부터 Windows 데스크톱 응용 프로그램에 이르기까지 다양한 프로그램을 만드는 데 사용할 수 있는 C 컴파일러가 포함되어 있습니다.  
  
 이 연습에서는 텍스트 편집기를 사용하여 기본적인 C 프로그램을 만들고 명령줄에서 컴파일하는 방법을 보여 줍니다.  
  
 이 연습에서 보여 주는 샘플 프로그램을 입력하는 대신 직접 작성한 C 프로그램을 사용할 수 있습니다.  도움말 항목에 들어 있는 C 코드 샘플 프로그램을 사용할 수도 있습니다.  
  
 기본적으로 Visual C\+\+ 컴파일러는 .c로 끝나는 파일은 모두 C 소스 코드로, .cpp로 끝나는 파일은 모두 C\+\+ 소스 코드로 취급합니다.  컴파일러가 파일 확장명에 관계없이 모든 파일을 C로 취급하도록 하려면 [\/Tc](../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션을 사용하세요.  
  
## 사전 요구 사항  
 개발자는 C 언어의 기본적인 사항을 알고 있어야 합니다.  
  
### C 소스 파일을 만들고 명령줄에서 컴파일하려면  
  
1.  개발자 명령 프롬프트를 엽니다.  Windows 8에서는 **시작** 화면에서 **Visual Studio Tools** 폴더를 연 다음 **개발자 명령 프롬프트** 바로 가기를 선택합니다.  이전 버전의 Windows에서는 **시작** 단추를 선택하고 **모든 프로그램**, **Microsoft Visual Studio** 및 **Visual Studio Tools**를 차례로 확장한 다음, **개발자 명령 프롬프트**를 선택합니다.  
  
     컴퓨터의 Windows 버전 및 시스템 보안 구성에 따라, 다음 단계를 수행하여 만드는 응용 프로그램을 빌드하고 실행하려면 **개발자 명령 프롬프트**의 바로 가기 메뉴를 열고 나서 **관리자 권한으로 실행**을 선택해야 할 수도 있습니다.  
  
    > [!NOTE]
    >  **개발자 명령 프롬프트**는 C 컴파일러 및 필요한 라이브러리의 올바른 경로를 자동으로 설정합니다.  일반 명령 프롬프트 창 대신 이 명령 프롬프트를 사용하세요.  자세한 내용은 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.  
  
2.  명령 프롬프트에서 소스 파일의 디렉터리를 만들고 현재 작업 디렉터리로 설정합니다.  예를 들어 **md c:\\simple**을 입력하고 Enter 키를 눌러 Simple이라는 디렉터리를 만든 다음 **cd c:\\simple**을 입력하고 Enter 키를 눌러 해당 디렉터리로 변경합니다.  
  
3.  명령 프롬프트에서 **notepad**를 입력하고 Enter 키를 누릅니다.  
  
4.  메모장에 다음 줄을 입력합니다.  
  
     [!code-cpp[NVC_Walkthrough_Compile_C#100](../build/codesnippet/CPP/walkthrough-compile-a-c-program-on-the-command-line_1.c)]  
  
5.  메뉴 모음에서 **파일**, **저장**을 차례로 선택하여 **다른 이름으로 저장** 대화 상자를 엽니다.  만든 디렉터리로 이동합니다.  **파일 이름** 상자에 소스 파일의 이름\(예: simple.c\)을 입력하고 **파일 형식** 드롭다운 목록에서 **모든 파일 \(\*.\*\)**을 선택합니다.  **저장** 단추를 선택하여 작업 디렉터리에 C 소스 파일을 만듭니다.  
  
6.  명령 프롬프트에서 **dir**을 입력하고 Enter 키를 누릅니다.  만든 소스 파일이 표시됩니다.  
  
  **C:\\simple\>dir**  
 **C 드라이브의 볼륨에는 레이블이 없습니다.  볼륨 일련 번호는 CC62\-6545입니다.**  
 **C:\\simple의 디렉터리**  
**10\/02\/2012  03:46 PM    \<DIR\>          .  10\/02\/2012  03:46 PM    \<DIR\>          ..  10\/02\/2012  03:36 PM               102 simple.c**  
 **1 File\(s\)            102 bytes**  
 **2 Dir\(s\)  514,900,566,016 bytes free**      세부 정보는 컴퓨터마다 다릅니다.  소스 코드 파일이 보이지 않는다면 만든 디렉터리로 변경했는지 확인하고 해당 위치에 .c 파일 이름 확장명을 사용하여 소스 파일을 저장했는지 확인합니다.  
  
7.  명령 프롬프트에서 소스 파일 이름과 함께 **cl** 명령\(예: **cl simple.c**\)을 지정하고 Enter 키를 눌러 프로그램을 컴파일합니다.  cl.exe 컴파일러는 컴파일된 코드가 포함된 .obj 파일을 생성합니다. 그리고 링커를 실행하여 .exe 파일 이름 확장명까지 포함된 소스 파일의 이름\(예: simple.exe\)이 포함된 실행 프로그램을 빌드합니다.  
  
     이 실행 가능한 프로그램의 이름이 컴파일러의 출력 정보 줄에 표시됩니다.  
  
     **출력**  
  
  **Microsoft \(R\) C\/C\+\+ 최적화 컴파일러 버전 17.00.50727.1\(x86\)**  
**Copyright \(c\) Microsoft Corporation.  All rights reserved.  simple.c**  
**Microsoft \(R\) Incremental Linker 버전 11.00.50727.1**  
**Copyright \(c\) Microsoft Corporation.  All rights reserved.  \/out:simple.exe**  
**simple.obj**      도구의 버전 번호는 설치한 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전 및 업데이트에 따라 달라집니다.  
  
    > [!NOTE]
    >  "'cl'은\(는\) 내부 또는 외부 명령, 실행할 수 있는 프로그램, 또는 배치 파일이 아닙니다."와 같은 오류나 오류 C1034 또는 오류 LNK1104가 표시되면 컴파일러 및 도구에 대한 환경을 설정해야 합니다.  자세한 내용은 1단계를 검토합니다.  
    >   
    >  컴파일러 오류 또는 경고가 발생하면 소스 코드에 오류가 있는지 검토하고 저장한 후 컴파일러를 다시 실행합니다.  특정 오류에 대한 자세한 내용은 이 페이지의 검색 상자를 사용합니다.  
  
8.  프로그램을 실행하려면 파일 이름 확장명 없이 이름\(예: **simple**\)을 입력하고 Enter 키를 누릅니다.  
  
     프로그램이 다음 텍스트를 표시하고 종료됩니다.  
  
     `This is a native C program.`  
  
## 참고 항목  
 [연습: Win32 콘솔 프로그램 만들기\(C\+\+\)](../windows/walkthrough-creating-a-standard-cpp-program-cpp.md)   
 [C 언어 참조](../c-language/c-language-reference.md)   
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)   
 [호환성](../c-runtime-library/compatibility.md)