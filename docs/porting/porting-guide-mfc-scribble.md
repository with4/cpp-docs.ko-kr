---
title: "포팅 가이드: MFC Scribble | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8ddb517d-89ba-41a1-ab0d-4d2c6d9047e8
caps.latest.revision: 5
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 포팅 가이드: MFC Scribble
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목은 이전 버전의 Visual Studio에서 만든 Visual C\+\+ 프로젝트를 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]로 업그레이드하는 절차를 소개하는 여러 항목 중 첫 번째입니다.  이러한 항목에서는 예를 들어 매우 간단한 프로젝트부터 좀더 복잡한 프로젝트로 이동하는 업그레이드 프로세스를 소개합니다.  이 항목에서는 MFC Sribble이라는 특정 프로젝트에 대한 업그레이드 프로세스를 안내합니다.  C\+\+ 프로젝트에 대한 업그레이드 프로세스의 기본 사항을 소개하는 데 적합합니다.  
  
 각 Visual Studio 버전에는 이전 버전의 Visual Studio에서 최신 버전으로의 코드 이동을 복잡하게 하는 비호환성이 있을 수 있습니다.  코드에 필요한 변경이 있어서 코드를 다시 컴파일하고 업데이트해야 하는 경우도 있고, 프로젝트 파일에 필요한 변경이 있는 경우도 있습니다.  이전 버전의 Visual Studio에서 만든 프로젝트를 여는 경우 Visual Studio에서 프로젝트 또는 솔루션을 최신 버전으로 업데이트할지 여부를 묻는 메시지를 자동으로 표시합니다.  이러한 도구는 일반적으로 프로젝트 파일만 업그레이드하고 소스 코드를 수정하지 않습니다.  
  
## MFC Scribble  
 MFC Scribble은 다양한 버전의 Visual C\+\+에 포함된 잘 알려진 샘플입니다.  MFC의 기본 기능 중 일부를 보여 주는 간단한 그리기 응용 프로그램입니다.  관리 코드 및 네이티브 코드 버전을 포함하여 다양한 버전으로 제공됩니다.  이 예제에서는 Visual Studio 2005에서 네이티브 코드로 작성된 이전 버전의 Scribble을 찾아 [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)]에서 열었습니다.  
  
 업그레이드하기 전에 전체 솔루션과 모든 콘텐츠를 백업합니다.  그런 다음 특정 업그레이드 방법을 결정해야 했습니다.  오랫동안 업그레이드되지 않은 더 복잡한 솔루션 및 프로젝트의 경우 한 번에 한 버전씩 Visual Studio 업그레이드를 고려해야 합니다.  이런 방식으로 문제가 발생한 Visual Studio 버전을 식별할 수 있습니다.  간단한 프로젝트의 경우 최신 버전의 Visual Studio에서 열고 마법사에서 프로젝트를 변환하도록 시도할 수 있습니다.  이 방법이 효과가 없을 경우 해당 버전의 Visual Studio에 액세스할 수 있으면 한 번에 한 버전씩 업그레이드를 시도할 수 있습니다.  
  
 마법사를 사용하여 프로젝트를 업그레이드하는 대신 `/Upgrade` 옵션을 사용하여 명령줄에서 devenv를 실행할 수도 있습니다.  [\/Upgrade](../Topic/-Upgrade%20\(devenv.exe\).md)를 참조하세요.  이 작업은 다수의 프로젝트에 대해 업그레이드 프로세스를 자동화하는 데 유용할 수 있습니다.  
  
### 1단계:프로젝트 파일 변환  
 Visual Studio 2015에서 이전 프로젝트 파일을 여는 경우 Visual Studio에서 프로젝트 파일을 최신 버전으로 변환하도록 제안하며, 이 제안을 수락했습니다.  다음과 같은 대화 상자가 나타납니다.  
  
 ![프로젝트 및 솔루션 변경 내용 검토](../porting/media/scribbleprojectupgrade.png "ScribbleProjectUpgrade")  
  
 Itanium 대상을 사용할 수 없어 변환되지 않는다고 알리는 오류가 발생했습니다.  
  
  **이 프로젝트에서 'Itanium' 플랫폼이 누락되었습니다.  이 플랫폼과 관련된 모든 구성 및 파일 구성 설정이 무시됩니다.  이 플랫폼을 변환하려는 경우 해당 플랫폼이 '%vctargetpath%\\platforms\\Itanium' 아래에 설치되어 있는지 확인하세요.  이 플랫폼 없이 이 프로젝트를 계속 변환하시겠어요?**  이전 Scribble 프로젝트를 만들 때 Itanium은 중요한 대상 플랫폼이었습니다.  Windows 플랫폼은 더 이상 Itanium을 지원하지 않으므로 Itanium 플랫폼을 지원하지 않고 계속하도록 선택했습니다.  
  
 그런 다음 visual Studio에서 이전 프로젝트 파일의 모든 문제를 나열하는 마이그레이션 보고서를 표시했습니다.  
  
 ![보고서 업그레이드](../porting/media/scribblemigrationreport.png "ScribbleMigrationReport")  
  
 이 경우 문제는 모두 경고였으며, Visual Studio에서 프로젝트 파일을 적절하게 변경했습니다.  프로젝트와 관련해서 가장 큰 차이점은 빌드 도구가 vcbuild에서 msbuild로 변경된 것입니다.  이 변경 내용은 Visual Studio 2010에서 처음 도입되었습니다.  기타 변경 내용에는 프로젝트 파일 자체의 요소 시퀀스 다시 정렬이 포함됩니다.  이 간단한 프로젝트에서 추가로 주의해야 할 문제는 없었습니다.  
  
### 2단계.빌드  
 빌드하기 전에 프로젝트 시스템에서 사용 중인 컴파일러 버전을 알 수 있도록 플랫폼 도구 집합을 확인합니다.  프로젝트 속성 대화 상자의 **구성 속성** 아래, **일반** 범주에서 **플랫폼 도구 집합** 속성을 확인합니다.  Visual Studio 버전 및 플랫폼 도구 버전 번호\(이 경우 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] 버전의 도구에 해당하는 v140\)이 포함되어 있습니다.  원래 Visual C\+\+ 2010, 2012 또는 2013을 사용하여 컴파일된 프로젝트를 변환하는 경우 도구 집합이 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] 도구 집합으로 자동으로 업데이트되지 않습니다.  Scribble의 경우 변환한 버전은 Visual Studio 2005용으로 생성되었으므로 최신 도구 집합을 사용하도록 변환되었습니다.  
  
 빌드 시 나타나는 첫 번째 문제는 MBCS 코드에 대한 것입니다.  
  
  **오류 MSB8031:**  오류 메시지의 링크는 Visual Studio 2013에서 MBCS의 사용 중단에 대한 항목으로 연결됩니다.  기본적으로 Visual C\+\+ 2013의 MFC 설치에는 MBCS 버전의 MFC가 포함되어 있지 않습니다.  MBCS 버전의 MFC는 현재 폼에서 이 프로젝트를 빌드하는 데 필요합니다.  유니코드를 사용하는 코드를 마이그레이션하거나, MBCS 버전의 MFC를 다운로드 및 설치할 수 있습니다.  MBCS 버전의 MFC를 다운로드하는 경우 이 경고를 표시하지 않으려면 NO\_WARN\_MBCS\_MFC\_DEPRECATION 매크로에 대한 정의를 추가할 수 있습니다.  
  
 MBCS 버전의 MFC를 다운로드하려면 먼저 [MFC MBCS DLL 추가 기능](../mfc/mfc-mbcs-dll-add-on.md) 문서 및 VC 블로그에서 MBCS 버전의 MFC 사용 중단에 대해 읽은 다음 [여기](http://www.microsoft.com/download/details.aspx?id=44930)서 MBCS 버전의 MFC를 다운로드합니다.  프로젝트 속성 대화 상자의 **C\/C\+\+** 범주 아래, **전처리기**의 미리 정의된 매크로 목록에 NO\_WARN\_MBCS\_MFC\_DEPRECATION을 추가합니다.  
  
 유니코드로 전환하려면 프로젝트의 속성을 열고 **구성 속성** 아래에서 **일반** 섹션을 선택한 다음 **문자 집합** 속성을 찾습니다.  이 속성을 **멀티바이트 문자 집합 사용**에서 **유니코드 문자 집합 사용**으로 변경합니다.  이렇게 변경하면 \_UNICODE 및 UNICODE 매크로가 정의되고 \_MBCS는 정의되지 않습니다. 이는 속성 대화 상자의 **C\/C\+\+** 범주 아래, **명령줄** 속성에서 확인할 수 있습니다.  
  
  **\/GS \/analyze\- \/W4 \/Gy \/Zc:wchar\_t \/Zi \/Gm\- \/O2 \/Ob1 \/Fd".  \\Release\\vc140.pdb" \/Zc:inline \/fp:precise \/D "\_AFXDLL" \/D "WIN32" \/D "NDEBUG" \/D "\_WINDOWS" \/D "\_UNICODE" \/D "UNICODE" \/errorReport:prompt \/GF \/WX \/Zc:forScope \/Gd \/Oy \/MD \/Fa".  \\Release\\" \/EHsc \/nologo \/Fo".  \\Release\\" \/Fp".  \\Release\\Scribble.pch"**  Scribble 프로젝트는 유니코드 문자를 사용하여 컴파일되도록 설정되지 않았지만 이미 char 대신 TCHAR로 작성되었으므로 실제로 변경해야 할 사항이 없습니다.  프로젝트가 유니코드 문자 집합을 사용하여 성공적으로 빌드됩니다.  
  
 그러나 다른 문제가 있습니다.  컴파일러에서 \_WINNT32\_WINNT가 정의되지 않았다고 알립니다.  
  
  **\_WIN32\_WINNT가 정의되지 않았습니다.  기본적으로 \_WIN32\_WINNT\_MAXVER로 설정됩니다\(WinSDKVer.h 참조\).**  이는 오류가 아니라 경고이며, Visual C\+\+ 프로젝트를 업그레이드할 때 흔히 발생합니다.  응용 프로그램이 실행되는 가장 낮은 버전의 Windows를 정의하는 매크로입니다.  경고를 무시하는 경우 현재 버전의 Windows를 의미하는 기본값 \_WIN32\_WINNT\_MAXVER을 수락하는 것입니다.  가능한 값의 테이블은 [Windows 헤더 사용](https://msdn.microsoft.com/en-us/library/aa383745.aspx)\(영문\)을 참조하세요.  예를 들어 Vista부터 모든 버전에서 실행되도록 설정할 수 있습니다.  
  
```  
#define _WIN32_WINNT _WIN32_WINNT_VISTA  
```  
  
 코드에서 이 매크로로 지정한 Windows 버전에서 사용할 수 없는 Windows API의 일부를 사용하는 경우 컴파일러 오류로 표시됩니다.  Scribble 코드의 경우 오류가 없습니다.  
  
### 3단계.테스트 및 디버깅  
 테스트 도구 모음이 없으므로 앱을 시작하고 UI를 통해 수동으로 해당 기능을 테스트했습니다.  문제가 발견되지 않았습니다.  
  
### 4단계.코드 개선  
 이제 Visual Studio 2015로 마이그레이션했으므로 새로운 C\+\+ 기능을 활용하기 위해 일부 변경 작업을 수행하는 것이 좋습니다.  현재 버전의 Visual C\+\+ 컴파일러는 이전 버전보다 C\+\+ 표준에 훨씬 더 부합되므로 코드를 더 안전하고 다른 컴파일러 및 운영 체제로 포팅하기 쉽게 변경하려는 경우 몇 가지 향상된 기능을 고려해야 합니다.  
  
## 다음 단계  
 Scribble은 작고 간단한 Windows 데스크톱 응용 프로그램이며 변환하기 어렵지 않았습니다.  마찬가지로, 대부분의 작고 간단한 앱은 쉽게 새 버전으로 변환됩니다.  많은 줄의 코드, 최신 엔지니어링 표준에 부합되지 않는 레거시 코드, 여러 프로젝트와 라이브러리, 사용자 지정 빌드 단계를 포함하는 더 복잡한 응용 프로그램이나 복잡한 스크립팅된 자동화 빌드의 경우 업그레이드하는 데 더 오랜 시간이 걸립니다.  [다음 예제](../porting/porting-guide-com-spy.md)인 COM Spy라는 ATL\/COM 응용 프로그램으로 계속합니다.  
  
## 참고 항목  
 [포팅 및 업그레이드: 예제 및 사례 연구](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [다음 예제: COM Spy](../porting/porting-guide-com-spy.md)