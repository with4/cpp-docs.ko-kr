---
title: "단계 0-Visual Studio에서 c + + 설치 지원 | Microsoft Docs"
description: "Visual c + +에 대 한 Visual Studio 지원 설치"
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 840f23d894e8aacc53a735fa8e1c25a671ed3a2a
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio에서 c + + 지원 설치

다운로드 하 고 Visual Studio 및 Visual c + + 도구를 아직 설치 하지 않은 경우 시작 방법은 다음과 같습니다.

## <a name="prerequisites"></a>필수 구성 요소

- 광대역 인터넷 연결 합니다. Visual Studio 설치 관리자는 여러 기가바이트 데이터를 다운로드할 수 있습니다.

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 개발 환경을 최적화 하려면 Windows 10이 좋습니다. Visual Studio를 설치 하기 전에 시스템에 최신 업데이트가 적용 되 고 있는지 확인 합니다.

- 디스크 공간이 부족 합니다. Visual Studio는 적어도 7 GB의 디스크 공간이 필요 하 고 많은 공통 옵션 설치 된 경우 50GB 이상 걸릴 수 있습니다. C: 드라이브에 설치 하는 것이 좋습니다.

디스크 공간 및 운영 체제 요구 사항에 대 한 세부 정보를 참조 하십시오. [Visual Studio 2017 시스템 요구 사항](https://www.visualstudio.com/productinfo/vs2017-system-requirements-vs)합니다. 설치 관리자에서 선택한 옵션에 대 한 필요한 디스크 공간을 보고 합니다.

## <a name="installation"></a>설치

1. Windows 용 최신 Visual Studio 2017 설치 관리자를 다운로드 합니다.

   > [!div class="nextstepaction"]
   > <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Community&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Community를 설치 합니다.</a>

   >[!Tip]
   > Community edition은 개별 개발자, 교실 학습, 학술 연구 및 오픈 소스 개발입니다. 다른 용도로 설치 <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Professional&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Professional</a> 또는 <a target="frameTarget" href="https://www.visualstudio.com/thank-you-downloading-visual-studio/?sku=Enterprise&rel=15&utm_source=docs&utm_medium=clickbutton">Visual Studio 2017 Enterprise</a>합니다.

1. 설치 관리자 파일을 다운로드 하 고 실행을 찾습니다. 브라우저에 표시 될 수 있습니다 또는 다운로드 폴더에서 찾을 수 있습니다. 설치 프로그램을 실행 하려면 관리자 권한이 필요 합니다. 표시 될 수 있습니다는 **사용자 계정 컨트롤** 설치 프로그램에서 시스템 변경할 이지만 선택할 수 있는 권한을 부여 하 라는 대화 **예**합니다. 문제가 있는 경우 파일 탐색기에서 다운로드 한 파일을 찾아서 설치 관리자 아이콘을 마우스 오른쪽 단추로 클릭 및 선택 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.

   ![Visual Studio 2017 설치 관리자 실행](../build/media/vscpp-concierge-run-installer.gif "Visual Studio 설치 관리자를 실행 합니다.")

1. 설치 관리자 작업은 특정 개발 영역에 대 한 관련된 옵션의 그룹 목록이 표시 됩니다. C + +에 대 한 지원을 기본적으로 설치 되어 있지 않으면 선택적 작업 부하의 일부 되었습니다.

   ![C + + 데스크톱 개발](../build/media/desktop-development-with-cpp.png "c + + 데스크톱 개발")

    C + +, 선택는 **c + + 데스크톱 개발** 작업 부하를 선택한 후 **설치**합니다.

   ![작업의 c + + 데스크톱 개발 설치](../build/media/vscpp-concierge-choose-workload.gif "작업의 c + + 데스크톱 개발을 설치 합니다.")

1. 설치가 완료 되 면 선택는 **시작** 단추를 Visual Studio를 시작 합니다.

   처음으로 Visual Studio를 실행 하면 Microsoft 계정으로 로그인 하 라는 메시지가 표시 됩니다. 하나에 없을 경우 무료로 만들 수 있습니다. 테마를 선택 해야 합니다. 스 러 하려는 경우 나중에 변경할 수 있습니다. 

   Visual Studio 여러 걸릴 수 있습니다에 하는 데 처음으로 사용 하기 위해 준비 된 실행 시간 (분)입니다. 모양에 경과 빠른 다음과 같습니다.

   ![Visual Studio 2017 로그인](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017에 로그인")

   Visual Studio는 다시 실행할 때 훨씬 빨리 시작 합니다.

1. Visual Studio가 열리면 확인 제목 표시줄에서 플래그 아이콘 강조 표시 됩니다.

   ![Visual Studio 2017 알림 플래그](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 알림 플래그")

   강조 표시 되는 경우 선택 엽니다는 **알림** 창. Visual Studio에 대 한 사용 가능한 업데이트가 있을 경우 지금 설치 하는 것이 좋습니다. 설치가 완료 되 면 Visual Studio를 다시 시작 합니다.

Visual Studio를 실행 하는 경우 다음 단계를 계속 진행할 준비가 됩니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [1 단계: c + + 프로젝트 만들기](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
