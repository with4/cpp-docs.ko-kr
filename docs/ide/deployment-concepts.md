---
title: 배포 개념 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4fa40373e268c76caca17f3466573bc3e830757
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="deployment-concepts"></a>배포 개념
이 섹션에서는 c + + 응용 프로그램 배포에 대 한 주요 고려 사항을 설명 합니다.  
  
## <a name="windows-installer-deployment-in-c"></a>C + +에서 Windows Installer 배포  
 Visual c + + 프로젝트는 일반적으로 배포를 위한 기존의 Windows Installer 설치 프로그램을 사용합니다. Windows Installer 배포를 준비 하려면 setup.exe 파일에서 응용 프로그램을 패키지 하는 설치 관리자 패키지 (.msi)와 함께 해당 파일을 배포 합니다. 그런 다음 사용자가 응용 프로그램을 설치 하려면 setup.exe를 실행 합니다.  
  
 설치 프로젝트를 솔루션; 추가 하 여 응용 프로그램 패키지 빌드할 때 파일을 만들 설치 및 설치 관리자 패키지 사용자에 게 배포 하는 합니다. 자세한 내용은 참조 [배포 방법 선택](../ide/choosing-a-deployment-method.md)합니다.  
  
## <a name="library-dependencies"></a>라이브러리 종속성  
 Visual c + + 라이브러리에서 제공 하는 기능을 사용 하는 C/c + + 응용 프로그램 작성 되 면 런타임에 해당 라이브러리의 존재 여부에 종속 됩니다. 실행할 응용 프로그램을 위해 링크 해야 정적 또는 동적으로 필요한 Visual c + + 라이브러리에 있습니다. 경우 응용 프로그램 동적으로 해당 라이브러리를 실행할 때 다음 Visual c + + 라이브러리에 링크 있어야 하므로 로드할 수 있습니다. 반면에 응용 프로그램이 Visual c + + 라이브러리에 정적으로 연결을 하는 경우 다음 필요는 없습니다 해당 Dll이 사용자의 컴퓨터에 존재 합니다. 하지만 정적 연결 몇 가지 단점이 같은 응용 프로그램 파일의 크기 증가 하 고 유지 관리 더 어렵습니다. 자세한 내용은 참조 [Dll 사용의 장점](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls)합니다.  
  
## <a name="packaging-and-redistributing"></a>패키징 및 재배포  
 Visual c + + 라이브러리 Dll로 패키지 됩니다 및 C/c + + 응용 프로그램에 필요한 모든 라이브러리는 Visual Studio에서 개발자의 컴퓨터에 설치 됩니다. 그러나 사용자에 게 응용 프로그램을 배포할 때는 없기 대부분의 경우 실현 응용 프로그램을 실행 하려면 Visual Studio를 설치 하도록 하 합니다. 해당 부분만 Visual c + + 응용 프로그램을 올바르게 실행에 필요한 재배포 하 하는 것이 유용 합니다.  
  
 패키징 및 재배포 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 합니다.  
  
-   [재배포할 Dll 확인](../ide/determining-which-dlls-to-redistribute.md)합니다.  
  
-   [배포 방법 선택](../ide/choosing-a-deployment-method.md)합니다.  
  
 배포 예제 및 문제 해결에 대 한 제안 사항에 대 한 참조.  
  
-   [배포 예제](../ide/deployment-examples.md)합니다.  
  
-   [격리 된 응용 프로그램 및 side-by-side-어셈블리 C/c + + 문제 해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Visual c + + 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer 배포](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)