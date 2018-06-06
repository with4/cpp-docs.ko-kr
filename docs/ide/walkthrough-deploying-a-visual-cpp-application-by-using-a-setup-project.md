---
title: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 454507a3a3f33b43af0e50c25dab6703aa75a56b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332782"
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>연습: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포
설치 프로젝트를 사용하여 Visual C++ 응용 프로그램을 배포하는 방법을 설명합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]가 설치된 컴퓨터  
  
-   Visual C++ 라이브러리가 없는 추가 컴퓨터  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>설치 프로젝트를 사용하여 응용 프로그램을 배포하려면  
  
1.  **MFC ApplicationWizard**를 사용하여 새 Visual Studio 솔루션을 만듭니다. 마법사를 찾으려면 **새 프로젝트** 대화 상자에서 **Visual C++** 노드를 확장하고, **MFC**를 선택하고, **MFC 응용 프로그램**을 선택하고, 프로젝트의 이름을 입력한 다음, **확인**을 클릭합니다.  
  
2.  활성 솔루션 구성을 **릴리스**로 변경합니다. **빌드** 메뉴에서 **Configuration Manger**를 선택합니다. **Configuration Manager** 대화 상자의 **활성 솔루션 구성** 드롭다운 상자 목록에서 **릴리스**를 선택합니다.  
  
3.  F7을 눌러 응용 프로그램을 빌드합니다. 또는 **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다. 그러면 설치 프로젝트가 이 MFC 응용 프로그램 프로젝트의 출력을 사용할 수 있습니다.  
  
4.  그렇게 하지 않은 경우 ISLE(InstallShield Limited Edition)을 다운로드합니다. 이 기능은 Visual Studio 개발자에게 무료로 제공되고, 설치 및 배포를 위해 Visual Studio에서 프로젝트 템플릿 기능을 대체합니다. 인터넷에 연결한 경우 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하거나 **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하거나 **추가**, **새 프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다. **기타 프로젝트 형식** 노드를 확장하고, **설치 및 배포** 노드에서 **InstallShield Limited Edition**을 선택하고, 표시되는 지침을 따릅니다. InstallShield Limited Edition을 다운로드하면 설치하고 활성화하고, Visual Studio를 닫았다가 다시 엽니다.  
  
5.  **새 프로젝트** 대화 상자를 다시 열고, **기타 프로젝트 형식** 노드를 확장하고,  **InstallShield Limited Edition** 노드에서 **InstallShield Limited Edition 프로젝트**를 선택합니다.  
  
6.  InstallShield Limited Edition 템플릿에서 만든 설치 프로젝트의 **시작** 노드 지침에 따라 Visual Studio MFC 프로젝트에 출력 참조를 추가합니다.  
  
7.  설치 관리자 파일(setup.exe)을 만들도록 설치 프로젝트를 빌드합니다. 이렇게 하려면 **솔루션 탐색기**에서 설치 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고, **빌드**를 선택합니다.  
  
     InstallShield Limited Edition은 설치 프로젝트 트리에서 설치 파일을 만듭니다(기본적으로 설치 프로젝트의 Express\SingleImage\DiskImages\DISK1 하위 폴더에 위치할 수 있음).  
  
8.  Visual C++ 라이브러리가 없는 두 번째 컴퓨터에서 설치 프로그램을 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)