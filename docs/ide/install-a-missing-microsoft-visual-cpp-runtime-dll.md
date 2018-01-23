---
title: "누락 된 Microsoft Visual c + + 런타임 DLL 설치 | Microsoft Docs"
description: "찾기 및 Visual c + + 런타임 Dll 누락을 설치 하는 방법."
ms.date: 08/30/2017
ms.topic: article
ms.prod: visual-cpp
dev_langs: C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9037a50740c55d7dd997fd86744459b6fb96125
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>누락 된 Microsoft Visual c + + 런타임 DLL을 설치 합니다.

종종 Microsoft Visual c + +를 사용 하 여 작성 된 프로그램에는 몇 가지 추가 Visual c + + 런타임 라이브러리 파일 또는 Dll을 실행 하려면 필요 합니다. 이러한 런타임 Dll에서 사용할 수 있는 한 *재배포 가능 패키지*, Visual c + +의 각 버전에 대 한 라이브러리 파일 설치 관리자 프로그램. 모든 프로그램에 필요한 재배포 가능 패키지는 해당 설치 관리자에 의해 포함 되어야 합니다. 없는 경우 때로는 재배포 가능 패키지를 직접 설치할 수 있고 프로그램을 실행 하는 경우 시스템 오류를 해결 합니다. 

프로그램 없음을 Visual c + + 런타임 DLL 할 프로그램을 시작할 때 시스템 오류가 발생 하면 알 수 있습니다 "프로그램을 컴퓨터에서 VCRuntime140.dll 없기 때문에 시작할 수 없습니다"와 동일한 합니다. 종종 프로그램을 제거한 다음 다시 설치 하 여이 문제를 해결할 수 있습니다. 이이 단계를 먼저 시도 전에 다른 잠재적 해결 방법.

경우에 따라 재배포 가능 패키지가 설치 프로그램에서 최신이 아닙니다. Microsoft에 게 런타임 Dll의 업데이트 된 버전 제공 수시로, 주소 버그 및 보안 문제입니다. 안전 하 게 하 고 정확 하 게 실행 하는 컴퓨터를 유지 하려면 모든 런타임 DLL에 대 한 최신 업데이트를 사용 하는 것이 좋습니다. 이 업데이트를 제공할 수 있는 프로그램에 사용할 수 있는 업데이트 된 설치 관리자 인지 확인 합니다. 없을 경우, 사용 하 여 업데이트 된 설치 관리자 프로그램을 다시 설치 하십시오.

프로그램을 다시 설치에 시스템 오류가 나타나지 않을 수는 없습니다, 프로그램 설치 관리자 수 손상 되거나 손상 다음 또는 컴퓨터에 런타임 Dll 손상 되었을 수 있습니다. 프로그램에 대 한 설치 관리자의 새 복사본을 다운로드 하 고 첫 번째 다시 설치 하는 데 사용 하려고 합니다. 문제가 해결 되지 않거나 설치 관리자를 사용할 수 없는, 다음 수도 있습니다 컴퓨터에 Microsoft Visual c + + 재배포 가능 패키지 설치를 확인 하는 것이 좋습니다. 

이 테이블에 대 한 링크를 재배포 가능 패키지의 복사본을 다운로드 하려면 하나 이상의 재배포 가능 패키지에 포함 된 Dll의 목록을 보여 줍니다. 재배포 가능 패키지의 새 복사본을 다운로드 하기 전에 기존 설치를 복구할 수는 경우 표시 됩니다.

|누락 된 DLL  |재배포 가능 패키지  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual c + + 2005 재배포 가능 (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Microsoft Visual c + + 2005 재배포 가능 패키지 (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[Microsoft Visual c + + 2005 서비스 팩 1 재배포 가능 패키지 MFC 보안 업데이트](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|atl90.dll<br />msvcr90.dll<br />msvcm90.dll<br />msvcp90.dll<br />mfc90.dll<br />mfc90u.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual c + + 2008 재배포 가능 패키지-x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual c + + 2008 재배포 가능 패키지-x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[Microsoft Visual c + + 2008 서비스 팩 1 재배포 가능 패키지 MFC 보안 업데이트](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|atl100.dll<br />msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual c + + 2010 x86 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual c + + 2010 x64 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[Microsoft Visual c + + 2010 서비스 팩 1 재배포 가능 패키지 MFC 보안 업데이트](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual c + + 2012 재배포 가능 구성 (Visual Studio 2012 업데이트 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Microsoft Visual c + + 2013 재배포 가능 패키지 (개별 다운로드 링크)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Visual Studio 2013 용 멀티 바이트 MFC 라이브러리](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[테스트용으로 로드 된 Windows 8.1 앱 (.zip 다운로드)에 대 한 visual c + + 2013 런타임](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual c + + 재배포 가능 (x86) 2017](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual c + + 재배포 가능 (x64) 2017](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[.NET Framework 다운로드](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>기존 재배포 가능 패키지를 복구 하려면

1. 제어판을 엽니다. Windows 10에서 입력 *제어판* 바탕 화면에 컨트롤의 작업 표시줄에서 검색 한 다음 선택 **제어판** 선택 항목에서 합니다.

2. 제어판에서 선택 **프로그램** > **프로그램 및 기능**합니다. Microsoft Visual c + + 재배포 가능 패키지 누락 된 DLL에 해당 하는 버전을 선택 합니다. 경우는 **변경** 선택 하는 목록 맨 위에 있는 단추가 나타납니다. 유일한 선택 이면 **제거**,이 버전의 재배포 가능 패키지를 복구할 수 없습니다.

3. 선택 **복구** 재배포 가능 패키지에 대 한 설정 대화 상자에서. 복구가 완료 되 면 다시 부팅 해야 합니다. 