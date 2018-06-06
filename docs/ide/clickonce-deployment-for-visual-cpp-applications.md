---
title: Visual C++ 응용 프로그램의 ClickOnce 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e85ec0dfc011aab4d2b3ac835bbe71782b055000
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33332327"
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Visual C++ 응용 프로그램의 ClickOnce 배포
Visual Studio는 Windows 응용 프로그램을 배포하기 위한 두 가지 기술인 ClickOnce 배포 및 [Windows Installer](http://msdn.microsoft.com/library/cc185688) 배포를 제공합니다.  
  
## <a name="clickonce-deployment-in-c"></a>C++의 ClickOnce 배포  
 Visual C++ 배포 환경에서는 ClickOnce를 사용한 Visual C++ 프로젝트 배포를 직접 지원하지 않지만 적절한 도구를 사용하면 이 방식으로 배포할 수 있습니다.  
  
> [!NOTE]
>  Visual Studio는 Visual C# 및 Visual Basic 개발 환경에서 ClickOnce를 지원합니다. Visual C++ 프로젝트가 Visual C# 프로젝트에 종속되어 있는 경우 Visual C# 배포 환경에서 ClickOnce 배포를 사용하여 응용 프로그램과 해당 종속 파일을 게시할 수 있습니다.  
  
 ClickOnce를 사용하여 Visual C++ 응용 프로그램을 배포하려면 먼저 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)를 사용하여 [ClickOnce 응용 프로그램 매니페스트](/visualstudio/deployment/clickonce-application-manifest) 및 [ClickOnce 배포 매니페스트](/visualstudio/deployment/clickonce-deployment-manifest) 또는 그래픽 사용자 인터페이스 버전을 빌드해야 합니다(자세한 내용은 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client) 참조).  

  
 우선 Mage.exe를 사용하여 응용 프로그램 매니페스트를 빌드합니다. 그 결과로 생성되는 파일의 확장명은 .manifest입니다. 그런 다음 Mage.exe를 사용하여 배포 매니페스트를 빌드합니다. 그 결과로 생성되는 파일의 확장명은 .application입니다. 마지막으로 매니페스트에 서명합니다.  
  
 응용 프로그램 매니페스트는 대상 프로세서(**x86**, **x64** 또는 **ARM**)를 지정해야 합니다. 이러한 옵션에 대한 자세한 내용은 [64비트 응용 프로그램의 필수 구성 요소 배포](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications)를 참조하세요.  
  
 또한 응용 프로그램 및 배포 매니페스트의 이름은 C++ 응용 프로그램의 이름과 달라야 합니다. 이는 Mage.exe에서 만든 응용 프로그램 매니페스트와 C++ 응용 프로그램의 일부인 외부 매니페스트 사이에 충돌이 발생하지 않도록 하기 위한 것입니다.  
  
 배포 시 응용 프로그램에 종속된 모든 Visual C++ 라이브러리를 설치해야 합니다. /DEPENDENTS 옵션을 지정하여 DUMPBIN 유틸리티를 사용하거나 depends.exe를 사용하면 특정 응용 프로그램에 대한 종속성을 확인할 수 있습니다. 종속성에 대한 자세한 내용은 [Visual C++ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)를 참조하세요. VCRedist.exe를 실행해야 할 수도 있습니다. 이 유틸리티는 대상 컴퓨터에 Visual C++ 라이브러리를 설치합니다.  
  
 필수 구성 요소를 배포하기 위해 응용 프로그램의 부트스트래퍼(필수 구성 요소 설치 관리자)를 빌드해야 할 수도 있습니다. 부트스트래퍼에 대한 자세한 내용은 [부트스트래퍼 패키지 만들기](/visualstudio/deployment/creating-bootstrapper-packages)를 참조하세요.  
  
 이 기술에 대한 자세한 내용은 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)를 참조하세요. ClickOnce 배포에 대한 자세한 예는 [연습: ClickOnce 응용 프로그램 수동 배포](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Mage.exe(매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe(매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe(인증서 작성 도구)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [응용 프로그램, 서비스 및 구성 요소 배포](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Windows Installer 배포](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce 보안 및 배포](/visualstudio/deployment/clickonce-security-and-deployment)   
 [부트스트래퍼 패키지 만들기](/visualstudio/deployment/creating-bootstrapper-packages)   
 [C++/CLI를 사용한 .NET 프로그래밍 (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)