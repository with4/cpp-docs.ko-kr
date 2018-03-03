---
title: "MFC 라이브러리 재배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca153ec9ca079bf13b1c1c1dcedd6e41497307f
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="redistributing-the-mfc-library"></a>MFC 라이브러리 재배포
MFC 라이브러리에 응용 프로그램에 동적으로 연결 하는 경우 일치 하는 MFC DLL을 재배포 해야 합니다. 예를 들어를 Visual Studio 2015와 함께 제공 되는 MFC의 버전을 사용 하 여 MFC 응용 프로그램을 빌드하는 경우 mfc140.dll 또는 좁은 문자 또는 유니코드 지원에 대 한 컴파일된 앱 여부에 따라 mfc140u.dll 재배포 해야 합니다.  
  
> [!NOTE]
>  Mfc140.dll 파일은 Visual Studio 2015 RTM에서 재배포 가능 파일 디렉터리에서 생략 되었습니다. 대신 Windows\syswow64 및 Windows\system32 디렉터리에서 Visual Studio 2015에서 설치할 버전을 사용할 수 있습니다.  
  
 MFC Dll의 모든 C 런타임 라이브러리 (CRT)의 공유 버전을 사용 하므로 CRT 재배포 할 수도 있습니다. Visual Studio 2015와 함께 제공 되는 mfc 버전 Windows 10의 일부로 배포 되는 범용 CRT 라이브러리를 사용 합니다. 이전 버전의 Windows에서 Visual Studio 2015를 사용 하 여 빌드한 MFC 응용 프로그램을 실행 하려면 유니버설 CRT를 재배포 해야 합니다. 참조 운영 체제 구성 요소로 하거나 로컬 배포를 사용 하 여 범용 CRT를 재배포 하는 방법에 대 한 내용은 [범용 CRT 소개](http://go.microsoft.com/fwlink/p/?linkid=617977)합니다. 지원 되는 버전의 Windows에서 중앙 배포에 대 한 유니버설 CRT를 다운로드 하려면 [Windows 10 유니버설 C 런타임](http://go.microsoft.com/fwlink/p/?LinkId=619489)합니다. 로컬 배포에 대 한 ucrtbase.dll의 재배포 가능한 아키텍처별 버전은 Windows SDK에 있습니다. 기본적으로 Visual Studio 설치 C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\에서 이러한 아키텍처 언어별 하위 디렉터리에서입니다.  
  
 를 이전 버전의 MFC 라이브러리를 사용 하 여 앱을 빌드하는 경우에 재배포 가능 파일 디렉터리에서 일치 하는 CRT DLL을 다시 배포 해야 합니다. 예를 들어를 Visual Studio 2013 (vc120) 도구 집합을 사용 하 여 MFC 응용 프로그램을 빌드하는 경우에: msvcr120.dll를 재배포 해야 합니다. 일치 하는 mfc를 재배포 해야`<version>`u.dll 또는 mfc`<version>`.dll입니다.  
  
 응용 프로그램을 MFC 정적으로 연결 되는 경우 (즉, 지정 하는 경우 **정적 라이브러리에서 MFC 사용** 에 **일반** 탭에 **속성 페이지** 대화 상자)를 필요가 없습니다 MFC DLL을 재배포 합니다. 그러나 정적 연결을 테스트에 사용할 수 있지만 응용 프로그램의 내부 배포 좋습니다는 사용 하지 않는 것 MFC를 재배포 합니다. Visual c + + 라이브러리를 배포 하기 위한 권장된 사항에 대 한 자세한 내용은 참조 [배포 방법 선택](../ide/choosing-a-deployment-method.md)합니다.  
  
 응용 프로그램에서는 WebBrowser 컨트롤을 구현 하는 MFC 클래스를 사용 하는 경우 (예를 들어 [CHtmlView 클래스](../mfc/reference/chtmlview-class.md) 또는 [CHtmlEditView 클래스](../mfc/reference/chtmleditview-class.md)), 최신 버전의도 설치 하는 것이 좋습니다 Microsoft Internet Explorer 수 있도록 대상 컴퓨터의 최신 공통 제어 파일. (여기에 최소한 Internet Explorer 4.0은 필요 합니다.) Internet Explorer 구성 요소를 설치 하는 방법에 대 한 정보는 Microsoft 지원 웹 사이트에서 "문서 185375:: 방법을를 만들기는 단일 EXE 설치의 Internet Explorer" 사용할 수 있습니다.  
  
 응용 프로그램에 MFC 데이터베이스 클래스 사용 하는 경우 (예를 들어 [CRecordset 클래스](../mfc/reference/crecordset-class.md) 및 [CRecordView 클래스](../mfc/reference/crecordview-class.md)), ODBC 및 응용 프로그램에서 사용 되는 모든 ODBC 드라이버를 다시 배포 해야 합니다. 자세한 내용은 참조 [데이터베이스 지원 파일 재배포](../ide/redistributing-database-support-files.md)합니다.  
  
 Windows Forms 컨트롤을 사용 하 여 MFC 응용 프로그램 mfcmifc80.dll 응용 프로그램과 함께 다시 배포 해야 합니다. 이 DLL은 해당 응용 프로그램 로컬 폴더에 재배포 하거나 사용 하 여 전역 어셈블리 캐시 (GAC)에 배포 하 여 응용 프로그램과 함께 재배포할 수 있는 강력한 이름 서명을.NET 어셈블리는 [Gacutil.exe (전역 어셈블리 캐시 도구)](/dotnet/framework/tools/gacutil-exe-gac-tool)합니다.  
  
 MFC DLL을 재배포 하는 경우에 일반 정품 버전 및 디버그 버전이 아니라 다시 배포 해야 합니다. Dll의 디버그 버전은 재배포할 수 없습니다. MFC Dll의 디버그 버전 이름은 끝나야는 "d", 예를 들어 Mfc140d.dll 합니다.  
  
 MFC VCRedist_ 중 하나를 사용 하 여 재배포할 수 있습니다*아키텍처*.exe, 병합 모듈을 응용 프로그램과 같은 폴더에 MFC DLL을 배포 하 여 또는 Visual Studio와 함께 설치 됩니다. MFC를 재배포 하는 방법에 대 한 자세한 내용은 참조 [Visual c + + 파일 재배포](../ide/redistributing-visual-cpp-files.md)합니다.  
  
## <a name="installation-of-localized-mfc-components"></a>지역화 된 MFC 구성 요소 설치  
 MFC 지역화 DLL을 설치 하 여 응용 프로그램을 지역화 하려는 경우에 재배포 가능 병합 파일 (.msm)를 사용 해야 합니다. 예: x86 응용 프로그램을 지역화 하려는 경우 컴퓨터 Microsoft_VC 병합 해야`<version>`x86에 대 한 설치 패키지에 _MFCLOC_x86.msm 컴퓨터입니다.  
  
 재배포 가능.msm 파일 지역화 하는 데 사용 되는 Dll이 포함 되어 있습니다. 지원 되는 각 언어에 대 한 하나의 DLL 있습니다. 설치 프로세스는 대상 컴퓨터에 %windir%\system32\ 폴더에 이러한 Dll을 설치합니다.  
  
 MFC 응용 프로그램을 지역화 하는 방법에 대 한 자세한 내용은 참조 하십시오. [TN057: MFC 구성 요소의 지역화](../mfc/tn057-localization-of-mfc-components.md), 그리고 [문서 208983: MFC를 사용 하 여 LOC Dll 하는 방법](http://go.microsoft.com/fwlink/p/?linkid=198025) Microsoft 지원 웹 사이트에서.  
  
 MFC 지역화 Dll은 MFC DLL 응용 프로그램 로컬 폴더에 배포 하 여 재배포할 수 있습니다. Visual c + + 라이브러리를 다시 배포 하는 방법에 대 한 자세한 내용은 참조 [Visual c + + 파일 재배포](../ide/redistributing-visual-cpp-files.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)