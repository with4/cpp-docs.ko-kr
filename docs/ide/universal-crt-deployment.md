---
title: 범용 CRT 배포 | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20006118d4bf27c379b78b84dc8807a4fd6c5e6c
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="universal-crt-deployment"></a>범용 CRT 배포

Visual Studio 2013을 통해 Visual Studio.NET에서 각 주요 릴리스는 c + + 컴파일러 및 도구는가 Microsoft CRT (C 런타임) 라이브러리의 새 독립 실행형 버전을 포함 합니다. 이러한 독립 실행형 버전의 CRT 이었다 보낸 사람 및 다양 한 수준으로 서로와 호환 되지 않습니다. 예를 들어 Visual Studio 2012에서 사용 되는 CRT 라이브러리 버전 11, 명명 된 msvcr110.dll, 한 Visual Studio 2013에서 사용 하는 CRT 버전 12, 명명 된: msvcr120.dll 였습니다. Visual Studio 2015부터,이 경우 더 이상는 합니다. Visual Studio 2015 및 이후 버전의 Visual Studio 모든 범용 CRT 인 하나를 사용합니다.

범용 CRT는 Microsoft Windows 운영 체제 구성 요소입니다. Windows 10에서 운영 체제의 일부로 포함 됩니다 하 고 Windows Update를 사용 하 여 Windows 8.1 통해 Windows Vista 이전 운영 체제에 사용할 수는 있습니다. 또한 몇 가지 제한 사항이 범용 CRT의 로컬 배포 지원 됩니다.

## <a name="central-deployment"></a>중앙 배포

중앙에서 범용 CRT를 설치 하려면 Microsoft Windows Update를 사용 하는 것이 좋습니다. 범용 CRT가 모두에 대 한 권장 업데이트에서 기본적으로 대부분의 컴퓨터가 설치 정기 업데이트 프로세스의 일환으로 Microsoft Windows 운영 체제를 지원 합니다. 범용 CRT의 초기 릴리스가 [KB2999226](https://support.microsoft.com/en-us/kb/2999226);에서 다양 한 버그 수정 된 이후 업데이트가 수행 되었습니다 [KB3118401](https://support.microsoft.com/en-us/kb/3118401), 추가 버그 픽스와 새로운 기능으로 추가 업데이트 되었습니다. 최신 업데이트에 대 한 검색 [support.microsoft.com](https://support.microsoft.com) 유니버설 C 런타임 또는 범용 CRT에 대 한 합니다.

일부 Microsoft Windows 컴퓨터 Windows Update를 사용 하 여 정기적으로 업데이트를 설치 하 고 일부 모든 권장 업데이트를 설치 하지 않을 수 있습니다. 컴퓨터에 Visual Studio 2015 및 최신 c + + 도구 집합을 사용 하 여 작성 된 응용 프로그램의 사용을 지원 하려면 없는 범용 CRT 인 재배포 가능 패키지 오프 라인 배포에 사용할 수 있는 합니다. 위의 KB 링크 중 하나에서 이러한 재배포 가능 패키지를 다운로드할 수 있습니다. 범용 CRT 인 재배포 가능 패키지는 컴퓨터는 현재 서비스 팩 하도록 업데이트 되었습니다 note 하십시오. 따라서 예를 들어 Windows 7 용 재배포 가능 패키지에서는 설치 되지 Windows 7 RTM Windows 7 s p 1에 합니다.

Visual c + + 재배포 가능 패키지 (VCRedist)에 이미 설치 됨, c + + 라이브러리를 충족 하기에 충분 한 버전을 설치 하지 않은 컴퓨터에 유니버설 CRT의 기본 버전을 설치 하는 범용 CRT 인 c + + 라이브러리의 기본 종속성 이기 때문에 종속성입니다. 응용 프로그램의 유니버설 CRT는 보다 최신 버전에 의존 하는 경우 명시적으로 해당 보다 최신 버전을 설치 해야 합니다. 다시 부팅 필요 잠재적인 다중을 방지 하기 위해 VCRedist를 설치 하기 전에이 설치 하는 것이 좋습니다.

## <a name="local-deployment"></a>로컬 배포

범용 CRT의 로컬 배포는 지원 되지 않지만 성능과 보안상의 이유로 모두에 적합 하지 않습니다.  로컬 배포에 대 한 Dll은 Windows 키트에는 Windows SDK의 일부로 포함\\10\\Redist\\ucrt\\컴퓨터 아키텍처에 의해 Dll 하위 디렉터리입니다. Dll ucrtbase.dll 등 APISet 전달자 Dll api 명명 된 집합이 필요한-ms-win-\*.dll입니다. 각 운영 체제에 필요한 Dll 집합 좋습니다 때 포함 하는 모든 Dll 로컬로 배포 되므로 달라 집니다.

주의 해야 할 로컬 배포에 두 가지 제한 사항이 있습니다.

- Windows 10에서 시스템 디렉터리에서 범용 CRT는 항상 사용 응용 프로그램의 유니버설 CRT는 응용 프로그램 로컬 복사본을 포함 하는 경우에 합니다. 범용 CRT의 로컬 복사본이 최신 이기 하는 경우에 마찬가지입니다. 즉, 유니버설 CRT는 Windows 10에서 핵심 운영 체제 구성 요소.

- Windows 8 이전 Windows 버전에는 범용 CRT 인 앱에 대 한 주 실행 파일을 포함 하는 디렉터리 아닌 다른 디렉터리에 있는 한 플러그인과 로컬로 패키지할 수 없습니다. APISet 전달자 Dll이 경우에 ucrtbase.dll를 성공적으로 해결 하지 못합니다. 일부 권장된 대체 솔루션은 다음과 같습니다.

  - 정적으로 링크 하는 범용 CRT 인,
  - 범용 CRT를 중앙에서 배포 또는
  - 범용 CRT 인 파일을 앱과 같은 디렉터리에 놓습니다.

## <a name="deployment-on-microsoft-windows-xp"></a>Microsoft Windows XP에는 배포

Visual Studio 2015 및 Visual Studio 2017는 계속 Microsoft Windows XP에서 사용 하기 위해 소프트웨어 개발을 지원 합니다. 이 지원 하려면 유니버설 CRT의 버전은 Microsoft Windows XP에서 연동 됩니다. Microsoft Windows XP 운영 체제는 더 이상 기본 또는 확장 지원 하므로 중앙 배포-Microsoft Windows XP에는 범용 CRT의 다른 운영 체제과에서 다릅니다.

Windows XP에는 Visual c + + 재배포 가능 설치 될 때 직접 설치 범용 CRT 및 모든 해당 종속성 시스템 디렉터리에 설치 하지 않고 또는 모든 Windows 업데이트에 따라 됩니다. 재배포 가능 병합 모듈을는 Microsoft_VC*버전*_CRT_\*.msm 파일을 동일한 작업을 수행 합니다.

Windows XP에서 범용 CRT의 로컬 배포 다른 지원 되는 운영 체제에서와 같습니다.

## <a name="see-also"></a>참고자료

- [Visual C++의 개발](deployment-in-visual-cpp.md)
