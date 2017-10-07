---
title: "Visual C++ 도구 집합의 문제를 보고하는 방법 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ec24a49c-411d-47ce-aa4b-8398b6d3e8f6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: 5c6fbfc8699d7d66c40b0458972d8b6ef0dcc705
ms.openlocfilehash: 2ea129ac94cb1ddc7486ba69280dc0390896e088
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="how-to-report-a-problem-with-the-visual-c-toolset"></a>Visual C++ 도구 집합의 문제를 보고하는 방법
Visual C++ 컴파일러, 링커 또는 기타 도구에 문제가 발생하면 문제를 파악하고자 합니다.  
  
 문제를 알리는 가장 좋은 방법은 발생한 문제에 대한 설명, 프로그램 빌드 방법에 대한 세부 정보 및 다른 컴퓨터에서 문제를 재현하는 데 사용할 수 있는 일부 코드를 포함하는 보고서를 보내는 것입니다. 이 정보를 통해 문제가 있고 사용자 환경에서만 발생하는 문제가 아님을 빠르게 확인할 수 있으며, 다른 버전의 컴파일러에 영향을 주는지 여부를 확인하고 원인을 진단할 수 있습니다.  
  
 이 문서의 내용은 다음과 같습니다.  
  
-   [보고서를 준비하는 방법](#prepare) 및 좋은 보고서의 요소  
  
-   [보고서를 보내는 방법](#send) 및 차이점  
  
-   [재현하는 방법](#generate) 및 다양한 종류의 재현  
  
 보고서는 Microsoft와 다른 개발자에게 중요합니다. Visual C++ 개선에 도움 주셔서 감사합니다!  
  
##  <a name="prepare"></a> 보고서를 준비하는 방법  
 완전한 정보가 없으면 발생한 문제를 다른 컴퓨터에서 재현하는 것이 매우 어렵기 때문에 고품질 보고서를 만드는 것이 중요합니다. 보고서가 향상될수록 더 효과적으로 문제를 재현하고 진단할 수 있습니다.  
  
 보고서에는 최소한 다음 정보가 포함되어야 합니다.  
  
-   사용 중인 도구 집합의 전체 버전 정보  
  
-   코드를 빌드하는 데 사용된 전체 cl.exe 명령줄  
  
-   발생한 문제에 대한 자세한 설명  
  
-   '재현' - 문제를 보여 주는 소스 코드  
  
 필요한 특정 정보와 이 정보를 확인할 수 있는 위치에 대해 자세히 읽어보세요.  
  
### <a name="the-toolset-version"></a>도구 집합 버전  
 다른 컴퓨터에서 동일한 도구 집합에 대해 재현을 테스트하기 위해 사용 중인 도구 집합의 전체 버전 정보가 필요합니다. 문제를 재현할 수 있는 경우 이 정보는 동일한 문제가 발생하는 다른 도구 집합 버전을 조사하는 시작점을 제공하기도 합니다.  
  
##### <a name="to-report-the-full-version-of-the-compiler-youre-using"></a>사용 중인 컴파일러의 전체 버전을 보고하려면  
  
1.  키보드에서 Windows 키를 누르고 `Developer Command Prompt` 입력을 시작합니다.  
  
2.  일치 항목 목록에 표시되는 경우 사용 중인 Visual Studio 버전과 일치하는 **개발자 명령 프롬프트** 버전을 선택합니다.  
  
3.  **개발자 명령 프롬프트** 콘솔에서 `cl /Bv /CLR` 명령을 입력합니다.  
  
 다음과 유사한 출력이 표시됩니다.  
  
```  
C:\Compiler>cl /Bv /CLR  
Microsoft (R) C/C++ Optimizing Compiler Version 18.00.40209  
for Microsoft (R) .NET Framework version 4.00.30319.34014  
Copyright (C) Microsoft Corporation.  All rights reserved.  
  
Compiler Passes:  
 C:\WinCComp\binaries.x86chk\bin\i386\cl.exe:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c1xx.dll:      Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\c2.dll:        Version 18.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\link.exe:      Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\mspdb120.dll:  Version 12.00.40209.0  
 C:\WinCComp\binaries.x86chk\bin\i386\1033\clui.dll: Version 18.00.40209.0  
 Common Language Runtime:                            Version  4.00.30319.34014  
  
cl : Command line error D8003 : missing source filename   
```  
  
 전체 출력을 복사하여 보고서에 붙여넣습니다.  
  
### <a name="the-command-line"></a>명령줄  
 다른 컴퓨터에서 동일한 방식으로 빌드하기 위해 코드를 빌드하는 데 사용된 전체 명령줄(cl.exe 및 인수)이 필요합니다. 발생한 문제가 특정 인수 또는 인수 조합을 사용하여 빌드하는 경우에만 나타날 수도 있기 때문에 이 정보는 중요합니다.  
  
 이 정보를 찾을 수 있는 최상의 위치는 문제가 발생한 직후의 빌드 로그입니다. 이렇게 하면 문제를 초래하는 동일한 인수가 명령줄에 정확히 포함됩니다.  
  
##### <a name="to-report-the-contents-of-the-command-line"></a>명령줄의 내용을 보고하려면  
  
1.  **CL.command.1.tlog** 파일을 찾아서 엽니다. 기본적으로 이 파일은 \\...\Visual Studio Version\Projects\SolutionName\ProjectName\Config\ProjectName.tlog\CL.command.1.tlog에 있습니다.  
  
     이 파일 내에서 소스 코드 파일의 이름과 각 파일을 컴파일하는 데 사용된 명령줄 인수를 각 줄에 하나씩 찾을 수 있습니다.  
  
2.  문제가 발생하는 소스 코드 파일의 이름을 포함하는 줄을 찾습니다. 그 아래 줄에는 해당 cl.exe 명령과 인수가 포함되어 있습니다.  
  
 전체 명령줄을 복사하여 보고서에 붙여넣습니다.  
  
### <a name="a-description-of-the-problem"></a>문제에 대한 설명  
 다른 컴퓨터에서도 동일한 결과가 표시되는지 확인할 수 있도록 발생한 문제에 대한 자세한 설명이 필요합니다. 이 정보는 수행하려던 작업과 예상한 동작을 파악하는 데에도 유용할 수 있습니다.  
  
 도구 집합에서 제공된 정확한 오류 메시지, 수행하려던 작업에 대한 간략한 설명(재현 코드 파악에 유용), 발견한 해결 방법 등 발생한 문제 진단에 도움이 되는 기타 세부 정보도 제공해 주세요. 보고서에 같은 정보를 반복해서 포함하지 마세요.  
  
### <a name="the-repro"></a>재현  
 다른 컴퓨터에서 오류를 재현할 수 있도록 발생한 문제를 보여 주는 자체 포함된 소스 코드 예제인 재현이 필요합니다. 발생한 문제 종류에 따라 보고서에 포함해야 하는 재현 종류가 결정됩니다. 적절한 재현이 없으면 아무것도 조사할 수 없습니다.  
  
 짧은 자체 포함된 재현은 보고서 텍스트에 직접 포함할 수 있지만, 큰 소스 코드 재현은 보고서에 첨부해야 합니다. 단일 소스 코드 파일로 줄일 수 없는 재현은 모든 파일이 포함된 디렉터리를 .zip 파일 등으로 압축하여 패키징하고 보고서에 첨부해야 합니다. 시나리오와 관련된 추가 세부 정보는 항상 보고서 텍스트에 포함해야 하며, 소스 코드에 포함하면 안 됩니다.  
  
 제공할 수 있는 최상의 재현 종류는 *최소 재현*입니다. 이는 문제를 보여 주기에 충분한 코드만 포함된 하나의 자체 포함된 소스 코드 파일(사용자 헤더에 대한 참조 없음)입니다. 이러한 형태의 재현을 제공할 수 있다면 소스 코드 파일을 보고서에 첨부하기만 하면 됩니다.  
  
 종속성이 없이 최소 재현으로 문제를 줄일 수 없는 경우 다음 섹션을 참조하여 보고서에 포함해야 하는 재현 종류를 확인하세요.  
  
#### <a name="frontend-parser-crash"></a>프런트 엔드(파서) 충돌  
 프런트 엔드 충돌은 컴파일러의 구문 분석 단계 중에 발생합니다. 일반적으로 컴파일러는 [심각한 오류 C1001](error-messages/compiler-errors-1/fatal-error-c1001.md)을 내보내고 오류가 발생한 소스 코드 파일 및 줄 번호를 참조합니다. msc1.cpp 파일을 언급하는 경우도 많지만 이 세부 정보는 무시해도 됩니다.  
  
 이러한 종류의 충돌을 보고하려면 [전처리 재현](#preprocessed_repro)을 제공하세요.  
  
 이러한 종류의 충돌에 대한 컴파일러 출력 예는 다음과 같습니다.  
  
```  
SandBoxHost.cpp  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        fatal error C1001: An internal error has occurred in the compiler.  
(compiler file 'msc1.cpp', line 1369)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
d:\o\dev\search\foundation\common\tools\sandbox\managed\managed.h(929):  
        note: This diagnostic occurred in the compiler generated function  
        'void Microsoft::Ceres::Common::Tools::Sandbox::SandBoxedProcess::Dispose(bool)'  
Internal Compiler Error in d:\o\dev\otools\bin\x64\cl.exe.  You will be prompted  
        to send an error report to Microsoft later.  
INTERNAL COMPILER ERROR in 'd:\o\dev\otools\bin\x64\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information   
```  
  
####  <a name="backend_crash"></a> 백 엔드(코드 생성) 충돌  
 백 엔드 충돌은 컴파일러의 코드 생성 단계 중에 발생합니다. 일반적으로 컴파일러는 [심각한 오류 C1001](error-messages/compiler-errors-1/fatal-error-c1001.md)을 내보내며, 문제와 관련된 소스 코드 파일 및 줄 번호를 참조하지 않을 수도 있습니다. compiler\utc\src\p2\main.c 파일을 언급하는 경우도 많지만 이 세부 정보는 무시해도 됩니다.  
  
 이러한 종류의 충돌을 보고하려면 [링크 재현](#link_repro)(LTCG(링크 타임 코드 생성)를 사용하는 경우) 또는 [전처리 재현](#preprocessed_repro)(LTCG를 사용하지 않는 경우)을 제공하세요. LTGC는 cl.exe에 대한 `/GL` 명령줄 인수를 통해 사용됩니다.  
  
 LTCG가 사용되지 **않는** 경우 이러한 종류의 충돌에 대한 컴파일러 출력 예는 다음과 같습니다. 컴파일러 출력이 이렇게 표시되는 경우 [전처리 재현](#preprocessed_repro)을 제공해야 합니다.  
  
```  
repro.cpp  
\\officefile\public\tadg\vc14\comperror\repro.cpp(13) : fatal error C1001:  
        An internal error has occurred in the compiler.  
(compiler file 'f:\dd\vctools\compiler\utc\src\p2\main.c', line 230)  
To work around this problem, try simplifying or changing the program near the  
        locations listed above.  
Please choose the Technical Support command on the Visual C++  
Help menu, or open the Technical Support help file for more information  
INTERNAL COMPILER ERROR in  
        'C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\BIN\cl.exe'  
    Please choose the Technical Support command on the Visual C++  
    Help menu, or open the Technical Support help file for more information  
```  
  
 **INTERNAL COMPILER ERROR**로 시작하는 줄에서 cl.exe 대신 link.exe가 언급되는 경우 LTCG가 사용된 것이며 [링크 재현](#link_repro)을 제공해야 합니다. 컴파일러 오류 메시지에서 LTCG 사용 여부가 확실하지 않은 경우 이전 단계에서 빌드 로그를 통해 복사한 명령줄 인수에서 `/GL` 명령줄 인수를 검사해야 할 수도 있습니다.  
  
#### <a name="linker-crash"></a>링커 충돌  
 링커 충돌은 컴파일러가 실행된 후 연결 단계 중에 발생합니다. 일반적으로 링커는 [링커 도구 오류 LNK1000](error-messages/tool-errors/linker-tools-error-lnk1000.md)을 내보냅니다.  
  
> [!NOTE]
>  출력에서 C1001이 언급되거나 링크 타임 코드 생성이 포함된 경우 대신 [백 엔드(코드 생성) 충돌](#backend_crash)에서 자세한 내용을 참조하세요.  
  
 이러한 종류의 충돌을 보고하려면 [링크 재현](#link_repro)을 제공하세요.  
  
 이러한 종류의 충돌에 대한 컴파일러 출력 예는 다음과 같습니다.  
  
```  
z:\foo.obj : error LNK1000: Internal error during IMAGE::Pass2  
  
  Version 14.00.22816.0  
  
  ExceptionCode            = C0000005  
  ExceptionFlags           = 00000000  
  ExceptionAddress         = 00007FF73C9ED0E6 (00007FF73C9E0000)  
        "z:\tools\bin\x64\link.exe"  
  NumberParameters         = 00000002  
  ExceptionInformation[ 0] = 0000000000000000  
  ExceptionInformation[ 1] = FFFFFFFFFFFFFFFF  
  
CONTEXT:  
  
  Rax    = 0000000000000400  R8     = 0000000000000000  
  Rbx    = 000000655DF82580  R9     = 00007FF840D2E490  
  Rcx    = 005C006B006F006F  R10    = 000000655F97E690  
  Rdx    = 000000655F97E270  R11    = 0000000000000400  
  Rsp    = 000000655F97E248  R12    = 0000000000000000  
  Rbp    = 000000655F97EFB0  E13    = 0000000000000000  
  Rsi    = 000000655DF82580  R14    = 000000655F97F390  
  Rdi    = 0000000000000000  R15    = 0000000000000000  
  Rip    = 00007FF73C9ED0E6  EFlags = 0000000000010206  
  SegCs  = 0000000000000033  SegDs  = 000000000000002B  
  SegSs  = 000000000000002B  SegEs  = 000000000000002B  
  SegFs  = 0000000000000053  SegGs  = 000000000000002B  
  Dr0    = 0000000000000000  Dr3    = 0000000000000000  
  Dr1    = 0000000000000000  Dr6    = 0000000000000000  
  Dr2    = 0000000000000000  Dr7    = 0000000000000000  
```  
  
 증분 연결이 사용되고 초기 연결 후에만(즉, 후속 증분 연결의 기준이 되는 첫 번째 전체 연결 후에만) 충돌이 발생한 경우 초기 연결이 완료된 후 수정한 소스 파일에 해당하는 개체(.obj) 및 라이브러리(.lib) 파일의 복사본도 제공해 주세요.  
  
#### <a name="bad-code-generation"></a>잘못된 코드 생성  
 잘못된 코드 생성은 드물지만 컴파일러에서 실수로 잘못된 코드가 생성되고 응용 프로그램이 컴파일 시간에 이 문제를 검색하지 못하고 런타임에 충돌하는 경우에 발생합니다. 발생하는 문제로 인해 잘못된 코드가 생성된다고 의심하는 경우 보고서를 [백 엔드(코드 생성) 충돌](#backend_crash)과 동일하게 처리하세요.  
  
 이러한 종류의 충돌을 보고하려면 [링크 재현](#link_repro)(LTCG(링크 타임 코드 생성)를 사용하는 경우) 또는 [전처리 재현](#preprocessed_repro)(LTCG를 사용하지 않는 경우)을 제공하세요. LTGC는 cl.exe에 대한 `/GL` 명령줄 인수를 통해 사용됩니다.  
  
##  <a name="send"></a> 보고서를 보내는 방법  
 여러 가지 방법으로 보고서를 보낼 수 있습니다. Microsoft Connect에서 버그를 신고하거나, 전자 메일을 보내거나, Visual Studio의 기본 제공 문제 보고 도구를 사용할 수 있습니다. 보고서에 적합한 선택 항목은 발생한 문제 종류, 보고서를 조사할 엔지니어와 상호 작용하려는 방법, 진행 상황을 추적하거나 보고서를 커뮤니티와 공유할지 여부에 따라 달라집니다.  
  
> [!NOTE]
>  보고서를 제출하는 방법에 관계없이 Microsoft는 사용자의 개인 정보를 보호합니다. Microsoft에서 사용자가 보낸 데이터를 처리하는 방법에 대한 자세한 내용은 [Microsoft Visual Studio 제품군 개인정보처리방침](https://www.visualstudio.com/dn948229)을 참조하세요.  
  
### <a name="file-a-bug-on-microsoft-connect"></a>Microsoft Connect에서 버그 신고  
 Microsoft Connect([connect.microsoft.com](http://connect.microsoft.com))에서는 사용자 커뮤니티가 Microsoft 제품을 빌드하는 팀에 직접 연결할 수 있습니다. Connect에서 새 버그를 신고하고, 기능 요청을 하고, 커뮤니티에서 제출된 다른 버그 및 요청을 보고, 자신에게 가장 중요한 사항을 알릴 수 있습니다.  
  
 보고서를 Visual Studio 커뮤니티와 공유하고 진행 상황을 추적하려는 경우 Connect 통해 문제를 보고하는 것이 가장 좋습니다. 보고서를 공유하면 다른 개발자가 해결 방법이나 문제 진단에 도움이 되는 추가 정보를 제공할 수도 있습니다. 보고서를 비공개로 유지하려는 경우(예: 보고서의 코드를 공유할 수 없는 경우)에도 Connect를 사용할 수 있으며, 양식을 제출하기 전에 보고서의 표시 유형을 비공개로 설정하기만 하면 됩니다.  
  
-   [Microsoft Connect: Visual Studio 2015 업데이트 3의 문제 보고](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6493)  
  
-   [Microsoft Connect: Visual Studio 2015 업데이트 2의 문제 보고](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6406)  
  
-   [Microsoft Connect: Visual Studio 2015 업데이트 1의 문제 보고](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6326)  
  
-   [Microsoft Connect: Visual Studio 2015의 문제 보고](https://connect.microsoft.com/VisualStudio/Feedback/LoadSubmitFeedbackForm?FormID=6240)  
  
 [Visual Studio 및 .NET Framework 피드백](https://connect.microsoft.com/VisualStudio/feedback/LoadSubmitFeedbackForm) Connect 페이지의 드롭다운에서 해당 제품을 찾아 다른 Visual Studio 및 .Net Framework 제품의 문제를 보고할 수 있습니다.  
  
### <a name="send-an-email"></a>전자 메일 보내기  
 전자 메일은 Visual C++ 팀에게 직접 보고서를 보내는 또 다른 방법입니다. [compilercrash@microsoft.com](mailto:compilercrash@microsoft.com)으로 전자 메일을 보내면 됩니다.  
  
 전자 메일을 통해 문제를 보고하는 경우 Microsoft Connect의 풍부한 커뮤니티는 없지만 큰 재현의 경우 더 효율적일 수도 있습니다. 또한 작업 환경이 인터넷에 연결되어 있지 않거나 다른 이유로 Microsoft Connect를 사용할 수 없는 경우 최상의 옵션이거나 유일한 옵션일 수 있습니다.  
  
 전자 메일을 통해 보고서를 보내는 경우 다음 템플릿을 전자 메일 메시지의 본문으로 사용할 수 있습니다. 전자 메일 본문에 해당 정보를 포함하지 않는 경우 소스 코드나 다른 파일을 첨부하세요.  
  
```  
To: compilercrash@microsoft.com  
Subject: Visual C++ Error Report  
-----  
  
Compiler version:  
  
CL.EXE command line:  
  
Problem description:  
  
Source code and repro steps:  
  
```  
  
### <a name="use-the-report-a-problem-tool"></a>문제 보고 도구 사용  
 Visual Studio의 문제 보고 도구는 Visual Studio 사용자가 마우스만 몇 번 클릭하여 다양한 문제를 보고할 수 있는 방법입니다. IDE를 벗어나지 않고 발생한 문제에 대한 자세한 정보를 지정한 다음 보고서를 제출하는 데 사용할 수 있는 간단한 양식을 제공합니다.  
  
 이 문서에 설명된 종류의 도구 집합 문제에서는 문제 보고 도구를 통해 문제를 보고하는 경우가 드물지만 원하는 경우 선택할 수 있는 옵션입니다.  
  
> [!TIP]
>  Visual Studio에서 발생할 수 있고 도구 집합과 관련이 없는 다른 종류의 문제(예: UI 문제, 손상된 IDE 기능 또는 일반 충돌)에서는 스크린샷 기능과 발생한 문제를 초래하는 UI 작업 기록 기능 때문에 문제 보고 도구가 특히 유용할 수 있습니다. Microsoft Connect도 이러한 다른 종류의 오류를 보고하는 데 적합할 수 있지만 문제 보고 도구의 추가 기능이 없습니다. 이러한 다른 종류의 오류는 compilercrash@microsoft.com으로 전자 메일을 전송하여 보고하면 안 됩니다.  
  
##  <a name="generate"></a> 보고서 생성  
 재현은 발생한 문제를 보여 주는 완전한 자체 포함된 코드 예제입니다. 재현은 코드 조각이 **아닙니다**. 보고하는 문제로 인해 생성되는 오류를 제외하고 빌드 및 실행되는 전체 예제여야 합니다. 표준 헤더의 경우에도 필요한 모든 #include 지시문을 포함해야 합니다.  
  
 또한 좋은 재현은 다음과 같습니다.  
  
-   **최소**. 재현은 발생한 문제를 정확하게 보여 주는 동시에 최대한 작아야 합니다. 재현이 복잡하거나 현실적일 필요는 없으며 간단하고 명료한 재현이 더 좋습니다. 작동하는 반대 예제를 포함할 필요는 없지만 설명에 도움이 되는 경우 포함할 수 있습니다. 문제를 초래하는 예제 코드만 있으면 됩니다.  
  
-   **자체 포함**. 재현에서 불필요한 종속성을 피해야 합니다. 가능한 한, 타사 라이브러리 없이 문제를 재현할 수 있도록 합니다. 가능한 한, 라이브러리 코드 없이 문제를 재현할 수 있도록 합니다(`std::out`, `printf()`는 사용 가능). 가능한 문제 원인으로 고려해야 하는 코드 양을 줄이면 도움이 됩니다.  
  
-   **최신 컴파일러 버전 사용**. 가능한 한, 재현에서 최신 버전의 도구 집합을 사용해야 합니다. 이전 버전의 도구 집합에서 발생할 수 있는 문제가 최신 버전에서는 수정된 경우가 많습니다.  
  
-   관련된 경우 **다른 컴파일러에서 확인**. 포팅 가능한 C++ 코드를 포함하는 재현은 가능한 경우 다른 컴파일러에서 동작을 확인해야 합니다.  
  
     이 단계는 코드가 올바른지(MSVC와 Clang 및 GCC에서 나타나는 결과가 다른 경우) 또는 잘못되었는지(MSVC, Clang 및 GCC에서 모두, 코드에서 오류가 생성되는 경우) 확인하는 데 도움이 됩니다.  
  
 다음은 각기 다른 종류의 문제를 보고하는 데 사용할 다양한 종류의 재현을 생성하기 위한 지침입니다.  
  
###  <a name="preprocessed_repro"></a> 전처리 재현  
 전처리 재현은 문제를 보여 주고 원래 소스 파일을 처리하여 C 전처리기의 출력에서 생성된 단일 소스 파일입니다. 이 프로세스에서는 포함된 헤더를 인라인으로 처리하여 추가 소스 및 헤더 파일에 대한 종속성을 제거하며 매크로, #ifdef 및 로컬 환경에 종속될 수 있는 다른 전처리기 명령도 확인합니다.  
  
> [!NOTE]
>  진행 중인 최신 구현을 대체하여 이미 문제가 해결되었는지 확인하는 경우가 많기 때문에, 전처리 재현은 표준 라이브러리 구현에 있는 버그의 결과로 나타날 수 있는 문제에는 적합하지 않습니다. 이 경우 재현을 전처리하지 말고, 문제를 단일 소스 파일로 줄일 수 없는 경우 코드를 .zip 파일 등으로 패키징하거나 IDE 프로젝트 재현을 사용하는 것이 좋습니다(아래의 [기타 재현](#other_repros) 참조).  
  
##### <a name="to-preprocess-a-source-code-file"></a>소스 코드 파일을 전처리하려면  
  
1.  키보드에서 Windows 키를 누르고 `Developer Command Prompt` 입력을 시작합니다.  
  
2.  일치 항목 목록에 표시되는 경우 사용 중인 Visual Studio 버전과 일치하는 **개발자 명령 프롬프트** 버전을 선택합니다.  
  
3.  **개발자 명령 프롬프트** 콘솔 창에서 `cl /P argumentsfilename.cpp` 명령을 입력합니다.  
  
 전처리된 파일(filename.i)이 생성된 후 전처리된 파일에서도 문제가 재현되는지 확인하는 것이 좋습니다. `/TP` 명령줄 인수를 사용하여 cl.exe에 전처리기 단계를 건너뛰고 정상적으로 컴파일을 시도하도록 지시할 수 있습니다.  
  
##### <a name="to-confirm-that-the-error-still-repros-with-the-preprocessed-file"></a>전처리된 파일에서도 오류가 재현되는지 확인하려면  
  
1.  키보드에서 Windows 키를 누르고 `Developer Command Prompt` 입력을 시작합니다.  
  
2.  일치 항목 목록에 표시되는 경우 사용 중인 Visual Studio 버전과 일치하는 **개발자 명령 프롬프트** 버전을 선택합니다.  
  
3.  **개발자 명령 프롬프트** 콘솔 창에서 `cl arguments /TP filename.i` 명령을 입력합니다.  
  
4.  문제가 재현되는지 확인합니다.  
  
 마지막으로, 이 재현을 보고서를 첨부합니다.  
  
###  <a name="link_repro"></a> 링크 재현  
 링크 재현은 링크 타임에 발생하는 문제(예: LTCG(링크 타임 코드 생성)와 관련된 백 엔드 충돌 또는 링커 충돌)를 총체적으로 보여 주는 빌드 아티팩트를 포함하는 단일 디렉터리입니다. 포함된 빌드 아티팩트는 문제를 재현할 수 있도록 링커 입력으로 필요한 항목입니다. 링크 재현은 링커를 통해 제공되는 기능을 사용하여 쉽게 만들 수 있습니다.  
  
##### <a name="to-generate-a-link-repro"></a>링크 재현을 생성하려면  
  
1.  명령 프롬프트를 열고 `mkdir directory` 명령을 입력하여 링크 재현에 대한 디렉터리를 만듭니다.  
  
2.  link_repro 환경 변수를 방금 만든 디렉터리로 설정합니다. `set link_repro=directory` 명령을 입력합니다.  
  
3.  Visual Studio 내에서 빌드를 수행하려는 경우 명령 프롬프트에서 `devenv` 명령을 입력하여 시작합니다. 이렇게 하면 link_repro 환경 변수의 값이 Visual Studio에 표시됩니다.  
  
4.  응용 프로그램을 빌드하고 예상한 문제가 발생하는지 확인합니다.  
  
5.  3단계에서 Visual Studio를 시작한 경우 이제 닫습니다.  
  
6.  link_repro 환경 변수를 지웁니다. `set link_repro=` 명령을 입력합니다.  
  
 마지막으로, 전체 디렉터리를 .zip 파일 등으로 압축하여 재현을 패키징하고 보고서에 첨부합니다.  
  
###  <a name="other_repros"></a> 기타 재현  
 문제를 단일 소스 파일이나 전처리 재현으로 줄일 수 없고 문제에 링크 재현이 필요하지 않은 경우 IDE 프로젝트를 조사할 수 있습니다. 프로젝트 내의 코드는 최소화해야 하며, 이 문서의 모든 지침도 적용됩니다.  
  
 재현을 최소 IDE 프로젝트로 만든 다음 전체 디렉터리 구조를 .zip 파일 등으로 압축하여 패키징하고 보고서에 첨부합니다.
