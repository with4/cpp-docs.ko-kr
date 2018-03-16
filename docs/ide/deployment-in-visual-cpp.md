---
title: "Visual c + +에서 배포 | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2018
ms.technology:
- cpp-ide
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2356e98e911978dcaef9471f2b474c2a2377716d
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="deployment-in-visual-c"></a>Visual C++의 개발

개발 컴퓨터 이외의 컴퓨터에서 응용 프로그램 설치 라고 *배포*합니다. 다른 컴퓨터에 Visual c + + 응용 프로그램을 배포 하는 경우 응용 프로그램과 모든 라이브러리 파일에 따라 달라 집니다를 설치 해야 합니다. Visual Studio를 사용 하면 해당 응용 프로그램과 함께 Visual c + + 라이브러리를 배포 하는 세 가지 방법으로: *중앙 배포*, *로컬 배포*, 및 *정적 링크*합니다. 중앙 배포-여기서는 Windows 업데이트 서비스 수를 자동으로 업데이트할 Windows 디렉터리 라이브러리 파일을 가져옵니다. 로컬 배포 응용 프로그램 같은 디렉터리에 라이브러리 파일을 저장합니다. 로컬 배포 된 모든 라이브러리를 다시 배포 해야 직접이 정보도 업데이트 합니다. 정적 연결 라이브러리 코드를 응용 프로그램에 바인딩합니다. 다시 컴파일해야 하 고 활용 하기 위해 모든 업데이트는 라이브러리에 정적 연결을 사용 하는 경우 응용 프로그램을 다시 배포 해야 합니다.

## <a name="central-deployment"></a>중앙 배포

Windows\System32 디렉터리 또는 x64 32 비트 라이브러리 파일에 대 한 중앙 배포 라이브러리 DLL 파일 설치 된 시스템, Windows\SysWow64 디렉터리입니다. Microsoft는 중앙 배포된 라이브러리를 자동으로 업데이트합니다. 로컬 배포 또는 정적으로 연결 하는 Visual c + + 라이브러리에 대 한 업데이트를 제공 해야 합니다.

Visual c + + 라이브러리를 중앙에서 배포 하려면 설치 하는 파일에 대 한 다음 두 가지 소스 중 하나의 사용할 수 있습니다.

- *재배포 가능 패키지* 파일은 압축 된 형태로 모든 Visual c + + 재배포 가능 라이브러리를 포함 하는 독립 실행형 명령줄 실행 파일, 또는

- *재배포 가능 병합 모듈* (.msm 파일) 및 응용 프로그램의 Windows Installer (.msi) 파일에 포함 하는 특정 라이브러리 배포에 사용할 수 있습니다.

재배포 가능 패키지 파일을 설치 하는 모든 Visual c + + 라이브러리는 특정 시스템 아키텍처에 대 한 합니다. 예를 들어 응용 프로그램은 작성 된 경우 x64, 응용 프로그램에서 사용 되는 모든 Visual c + + 라이브러리를 설치 해야 vcredist_x64.exe 재배포 가능 패키지를 사용할 수 있습니다. 응용 프로그램을 설치 하기 전에 필수 구성 요소 재배포 가능 패키지를 실행 하려면 응용 프로그램 설치 관리자를 프로그래밍할 수 있습니다.

병합 모듈의 Windows Installer 응용 프로그램 설치 파일에 특정 Visual c + + 라이브러리에 대 한 설치 논리를 포함할 수 있습니다. 응용 프로그램에 필요한 만큼 또는 적은 병합 모듈을 포함할 수 있습니다. 배포 이진 파일의 크기를 최소화 해야 할 때 병합 모듈을 사용 합니다.

라이브러리 Dll을 사용 하 여 정적 라이브러리 대신 응용 프로그램에서 중앙 사용 하는 권장 중앙 배포-병합 모듈 또는 재배포 가능 패키지를 사용 하 여 Visual c + + 라이브러리를 자동으로 업데이트 하도록 Windows Update를 통해 수, 로컬 배포 하는 대신 배포 합니다.

## <a name="local-deployment"></a>로컬 배포

로컬 배포의 경우 라이브러리 파일은 실행 파일과 함께 응용 프로그램 폴더에 설치 됩니다. 각 버전의 파일 이름은 버전 번호를 포함 하기 때문에 서로 다른 버전의 Visual c + + 재배포 가능 라이브러리와 동일한 폴더에 설치할 수 있습니다. 예를 들어, c + + 런타임 라이브러리의 버전 12 msvcp120.dll, 및 14는 msvcp140.dll 버전입니다.

라이브러리 라고 하는 여러 추가 Dll 분산 될 수 *라이브러리 점*합니다. 예를 들어 Visual Studio 2017 버전 15.6에에서 릴리스 표준 라이브러리의 일부 기능에 추가 되었습니다 msvcp140_1.dll에 preverve msvcp140.dll의 ABI 호환성. Visual Studio 2017 버전 15.6 (도구 집합 14.13) 또는 Visual Studio 2017에서 최신 도구 집합을 사용 하는 경우 로컬에서 이러한 점 라이브러리 뿐 아니라 주 라이브러리를 배포 해야 할 수 있습니다. 이러한 별도 점 라이브러리 ABI 변경 될 때 다음 기본 라이브러리의 다음 주 버전으로 롤백됩니다.

Microsoft 없습니다 자동으로 하기 때문에 업데이트를 로컬로 Visual c + + 라이브러리를 배포, 이러한 라이브러리의 로컬 배포 권장 하지는 않습니다. 재배포 가능 라이브러리 로컬 배포를 사용하기로 결정하는 경우 로컬 배포된 라이브러리를 자동으로 업데이트하는 사용자 고유의 메서드를 구현하는 것이 좋습니다.

## <a name="static-linking"></a>정적 링크

동적으로 연결 된 라이브러리 외에도 Visual Studio 정적 라이브러리도 대부분의 라이브러리를 제공합니다. 정적으로 링크는 정적 라이브러리 응용 프로그램에 즉, 라이브러리 개체 코드는 응용 프로그램에 직접 연결할 수 있습니다. 이 생성 되어 DLL 종속성 없이 단일 이진 Visual c + + 라이브러리 파일을 별도로 배포할 필요가 없습니다. 그러나 권장 하지는 않습니다이 방법은 정적 연결 라이브러리 위치에서 업데이트할 수 없기 때문에 있습니다. 정적 연결을 사용하고 연결된 라이브러리를 업데이트하려면 응용 프로그램을 다시 컴파일하고 다시 배포해야 합니다.

## <a name="troubleshooting-deployment-issues"></a>배포 문제 해결

Visual c + + 라이브러리의 로드 순서는 시스템에 따라 다릅니다. 로더 문제를 진단하려면 depends.exe 또는 where.exe를 사용합니다. 자세한 내용은 참조 [동적 연결 라이브러리 검색 순서 (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)합니다.

## <a name="see-also"></a>참고 항목

[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)