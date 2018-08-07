---
title: Visual Studio에서 c + + 지원 설치 | Microsoft Docs
description: Visual Studio의 Visual c + + 지원 설치
ms.custom: mvc
ms.date: 06/21/2018
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8043ff1c25c08c6adcb640defba1bc967a2fb8b
ms.sourcegitcommit: 66f4f12d3851c897ca69cf62da1697e95b2b97c2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39496560"
---
# <a name="install-c-support-in-visual-studio"></a>Visual Studio에서 c + + 지원 설치

다운로드 하 고 Visual Studio 및 Visual c + + 도구를 아직 설치 하지 않은 경우 시작 하는 방법을 다음과 같습니다.

## <a name="prerequisites"></a>전제 조건

- 광대역 인터넷 연결 합니다. Visual Studio 설치 관리자를 여러 기가바이트 단위의 데이터를 다운로드할 수 있습니다.

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 최상의 개발 환경을 위해 Windows 10이 좋습니다. Visual Studio를 설치 하기 전에 시스템에 최신 업데이트가 적용 되 고 있는지 확인 합니다.

- 사용 가능한 디스크 공간이 충분 합니다. Visual Studio는 7GB 이상 디스크 공간이 필요 하 고 다양 한 일반 옵션 설치 된 경우 50GB 이상 걸릴 수 있습니다. C: 드라이브에 설치 하는 것이 좋습니다.

디스크 공간 및 운영 체제 요구 사항에 대 한 자세한 내용은 참조 하세요. [Visual Studio 제품군 시스템 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-vs)합니다. 설치 관리자에서 선택한 옵션에 대 한 필요한 디스크 공간을 보고 합니다.

## <a name="installation"></a>설치

1. Windows에 대 한 최신 Visual Studio 2017 설치 관리자를 다운로드 합니다.

   > [!div class="nextstepaction"]
   > [Visual Studio 2017 Community 설치](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

   >[!Tip]
   > 커뮤니티 에디션은 개인 개발자, 교실 학습, 학술 연구 및 오픈 소스 개발용입니다. 다른 용도의 경우 [Visual Studio 2017 Professional](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 또는 [Visual Studio 2017 Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)를 설치합니다.

1. 다운로드 하 고 실행 하면 설치 관리자 파일을 찾습니다. 브라우저에서 표시 될 수 있습니다 또는 다운로드 폴더에서 찾을 수 있습니다. 설치 관리자를 실행 하려면 관리자 권한이 필요 합니다. 표시 될 수 있습니다는 **사용자 계정 컨트롤** 설치 프로그램에서 시스템 변경; 선택 권한을 부여 하려면 묻는 대화 상자 **예**합니다. 문제가 있는 경우 파일 탐색기에서 다운로드 한 파일을 찾을 설치 관리자 아이콘을 마우스 오른쪽 단추로 클릭 선택할 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.

   ![Visual Studio 2017 설치 관리자를 실행](../build/media/vscpp-concierge-run-installer.gif "Visual Studio 설치 관리자를 실행 합니다.")

1. 설치 관리자는 특정 개발 영역에 대한 관련 옵션의 그룹인 워크로드 목록을 제공합니다. C + +에 대 한 지원은 이제 기본적으로 설치 되지 않은 선택적 워크 로드의 일부입니다.

   ![C + +를 사용한 데스크톱 개발](../build/media/desktop-development-with-cpp.png "c + +를 사용한 데스크톱 개발")

    C + +를 선택 합니다 **c + +를 사용한 데스크톱 개발** 워크 로드를 선택한 후 **설치**합니다.

   ![C + + 워크 로드를 사용 하 여 데스크톱 개발을 설치](../build/media/vscpp-concierge-choose-workload.gif "c + + 워크 로드를 사용 하 여 데스크톱 개발을 설치 합니다.")

1. 설치가 완료 되 면 선택 합니다 **시작** Visual Studio를 시작 하는 단추입니다.

   처음 Visual Studio를 실행 하면 Microsoft 계정으로 로그인 하 라는 메시지가 표시 됩니다. 사용자 계정이 없는 경우 무료로 만들 수 있습니다. 테마를 선택 해야 합니다. 작업을 하려는 경우 나중에 변경할 수 있습니다. 

   Visual Studio 여러 걸릴 수 있습니다 분에 대해 준비 하려면 처음으로 사용 하 여 실행 합니다. 모양을 빠른 시간 경과에 다음과 같습니다.

   ![Visual Studio 2017에 로그인](../build/media/vscpp-quickstart-first-run.gif "Visual Studio 2017에 로그인")

   Visual Studio는 다시 실행 하면 훨씬 더 빠르게 시작 합니다.

1. Visual Studio가 열리면 제목 표시줄에서 플래그 아이콘을 강조 표시 된 경우를 확인 합니다.

   ![Visual Studio 2017의 알림 플래그](../build/media/vscpp-first-start-page-flag.png "Visual Studio 2017 알림 플래그")

   이 강조 표시 하는 경우 선택 하 여 엽니다는 **알림을** 창입니다. Visual Studio에 대 한 사용 가능한 모든 업데이트가 있는 경우 지금 설치 하는 것이 좋습니다. 설치가 완료 되 면 Visual Studio를 다시 시작 합니다.

Visual Studio를 실행 하는 경우 다음 단계를 계속 준비가 되었습니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [C + + 프로젝트 만들기](vscpp-step-1-create.md)

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
