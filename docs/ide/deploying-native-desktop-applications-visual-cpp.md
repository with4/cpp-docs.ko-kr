---
title: 네이티브 데스크톱 응용 프로그램 배포(Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f4aa355c132b4c94f085cbdf7aa73785357d0f0
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34259246"
---
# <a name="deploying-native-desktop-applications-visual-c"></a>네이티브 데스크톱 응용 프로그램 배포(Visual C++)

배포는 다른 컴퓨터에 설치할 완성된 응용 프로그램이나 구성 요소를 배포하는 프로세스입니다. 배포 계획은 개발자의 컴퓨터에 응용 프로그램을 만들 때 시작되고, 응용 프로그램이 설치되고 사용자의 컴퓨터에서 실행할 준비가 되면 배포가 종료됩니다.

Visual Studio는 Windows 응용 프로그램을 배포하는 다양한 기술을 제공합니다. 여기에는 ClickOnce 배포 및 Windows Installer 배포가 포함됩니다.

- ClickOnce는 혼합형, 순수형 및 안정형 어셈블리의 CLR(공용 언어 런타임)을 대상으로 하는 C++ 응용 프로그램 배포에 사용할 수 있습니다. Windows Installer를 사용하여 관리되는 응용 프로그램을 배포할 수 있지만 매니페스트 서명과 같은 .NET Framework 보안 기능을 활용할 수 있으므로 ClickOnce를 사용하는 것이 좋습니다. ClickOnce는 네이티브 C++ 응용 프로그램의 배포를 지원하지 않습니다. 자세한 내용은 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)를 참조하세요.

- Windows Installer 기술은 네이티브 C++ 응용 프로그램 또는 CLR를 대상으로 하는 C++ 응용 프로그램을 배포하는 데 사용할 수 있습니다.

설명서의 이 단원에 있는 문서는 네이티브 Visual C++ 응용 프로그램이 지원되는 대상 플랫폼을 제공하는 컴퓨터에서 실행되도록 하는 방법, 설치 패키지에 포함해야 하는 파일 및 응용 프로그램이 종속된 구성 요소를 재배포하는 데 권장되는 방법에 대해 설명합니다.

## <a name="in-this-section"></a>섹션 내용

- [Visual C++의 개발](../ide/deployment-in-visual-cpp.md)

- [배포 개념](../ide/deployment-concepts.md)

- [Visual C++ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)

- [재배포할 DLL 확인](../ide/determining-which-dlls-to-redistribute.md)

- [배포 방법 선택](../ide/choosing-a-deployment-method.md)

- [범용 CRT 배포](universal-crt-deployment.md).

- [Visual C++ 파일 재배포](../ide/redistributing-visual-cpp-files.md)

- [배포 예제](../ide/deployment-examples.md)

- [웹 클라이언트 응용 프로그램 재배포](../ide/redistributing-web-client-applications.md)

- [Visual C++ 응용 프로그램의 ClickOnce 배포](../ide/clickonce-deployment-for-visual-cpp-applications.md)

- [이전 버전의 런타임에서 C++ /clr 응용 프로그램 실행](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>관련 단원

- [C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [배포](/dotnet/framework/deployment/index)

- [ 격리된 응용 프로그램 및 side-by-side 어셈블리 문제 해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)