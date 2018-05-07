---
title: '연습: 프로그램 (c + +)를 배포 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], walkthroughs
- setup projects [C++]
- program deployments [C++]
- projects [C++], setup
- projects [C++], deploying programs
- application deployment [C++], walkthroughs
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1753c63673b9dd083e2b690788801bd467938c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-your-program-c"></a>연습: 프로그램 배포(C++)
이전 관련된 연습을에 나열 된 완료 하 여 응용 프로그램을 만든 다음에 이제 [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md), 마지막 단계는 다른 사용자가 수행할 수 있도록 하는 설치 관리자를 만드는 것 자신의 컴퓨터에서 프로그램을 설치 합니다. 이렇게 하려면 기존 솔루션에 새 프로젝트를 추가합니다. 이 새 프로젝트에서 다른 컴퓨터에 응용 프로그램을 설치하는 setup.exe 파일이 생성됩니다.  
  
 이 연습에서는 Windows Installer를 사용하여 응용 프로그램을 배포하는 방법을 보여 줍니다. ClickOnce를 사용하여 응용 프로그램을 배포할 수도 있습니다. 자세한 내용은 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)를 참조하세요. 배포에 대 한 자세한 내용은 참조 일반적으로 [응용 프로그램 배포, 서비스 및 구성 요소](/visualstudio/deployment/deploying-applications-services-and-components)합니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
-   이 연습에서는 사용자가 C++ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 이전 관련된 연습에 나와 있는 완료 한 것으로 가정 [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)합니다.  
  
-   Visual Studio Express Edition에서는 이 연습을 수행할 수 없습니다.  
  
-   아직 연습을 수행하지 않았으면 이 문서 뒷부분의 설명에 따라 ISLE(InstallShield Limited Edition)를 다운로드합니다. ISLE은 Visual Studio 개발자를 위한 무료 버전이며 이전 Visual Studio 버전의 설치 및 배포 프로젝트 템플릿 기능을 대체합니다.  
  
### <a name="to-install-the-isle-setup-and-deployment-project-template"></a>ISLE 설치 및 배포 프로젝트 템플릿을 설치하려면  
  
1.  메뉴 모음에서 인터넷에 연결 되어 있는 경우 선택 **파일**, **새로**, **프로젝트** 열려는 **새 프로젝트** 대화 상자.  
  
2.  대화 상자의 왼쪽된 창에서 확장 된 **설치 됨**, **템플릿**, 및 **기타 프로젝트 형식** 노드를 선택한 후 **설치 및 배포**. 가운데 창에서 선택 **InstallShield Limited Edition** 선택한 후는 **확인** 단추입니다.  
  
3.  지침을 따라 InstallShield Limited Edition for Visual Studio(ISLE)를 설치합니다.  
  
4.  ISLE를 다운로드, 설치 및 정품 인증한 후 Visual Studio를 닫았다가 다시 엽니다.  
  
5.  메뉴 모음에서 **파일**, **최근 프로젝트 및 솔루션**를 선택한 후는 **게임** 솔루션 파일을 다시 합니다.  
  
### <a name="to-create-a-setup-project-and-install-your-program"></a>설치 프로젝트를 만들고 프로그램을 설치하려면  
  
1.  활성 솔루션 구성을 릴리스로 변경합니다. 메뉴 모음에서 **빌드**, **구성 관리자**를 선택합니다. 에 **Configuration Manager** 대화 상자의 **활성 솔루션 구성** 드롭 다운 목록 **릴리스**합니다. 선택 된 **닫기** 구성을 저장 하는 단추입니다.  
  
2.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 열려는 **새 프로젝트** 대화 상자.  
  
3.  대화 상자의 왼쪽된 창에서 확장 된 **설치 됨**, **템플릿**, 및 **기타 프로젝트 형식** 노드를 선택한 후 **설치 및 배포**. 가운데 창에서 선택 **InstallShield Limited Edition 프로젝트**합니다.  
  
4.  설치 프로젝트에 대 한 이름을 입력 된 **이름** 상자입니다. 이 예에서는 입력 **Game Installer**합니다. 에 **솔루션** 드롭 다운 목록 **솔루션에 추가**합니다. 선택 된 **확인** 설치 프로젝트를 만드는 단추입니다. A **프로젝트 도우미 (게임 설치 관리자)** 편집기 창에서 탭이 열립니다.  
  
5.  맨 아래에 **프로젝트 도우미 (게임 설치 관리자)** 탭에서 선택 된 **응용 프로그램 정보** 링크 합니다.  
  
6.  에 **응용 프로그램 정보** 페이지에서 설치 관리자에서 원하는 만큼 회사 이름을 지정 합니다. 자신의 회사 이름을 사용 하거나이 예제에서는 사용할 수 있습니다 **Contoso**합니다. 응용 프로그램 이름, 이 예제에서는 지정 **게임**합니다. 회사 웹 사이트 주소를 지정 하거나이 예제에 대 한 사용 **http://www.contoso.com**합니다.  
  
7.  맨 아래에 **프로젝트 도우미 (게임 설치 관리자)** 탭에서 선택 된 **설치 인터뷰** 링크 합니다.  
  
8.  에 **설치 인터뷰** 페이지의 **사용권 계약 대화 상자를 표시 하 시겠습니까**선택는 **아니요** 옵션 단추입니다. **사용자 이름과 사용자가 자신의 회사 이름을 입력 하도록 메시지를 표시 하 시겠습니까**선택는 **아니요** 옵션 단추입니다.  
  
9. **솔루션 탐색기**를 확장 하 고는 **Game Installer** 프로젝트를 확장 하 고는 **Organize Your Setup** 노드를 연 후는 **일반정보** 페이지.  
  
10. 에 **General Information (Game Installer)** 편집기 창에서 탭을 지정는 **태그 생성 ID**, 예를 들어 **-: regid.2012-12.com.contoso**합니다.  
  
11. **솔루션 탐색기**아래는 **Game Installer** 프로젝트를 확장 하 고는 **응용 프로그램 데이터 지정** 노드를 연 후는 **파일** 페이지입니다.  
  
12. 에 **Files (Game Installer)** 아래의 편집기 창에서 탭 **원본 컴퓨터의 파일**, 바로 가기 메뉴를 열고 **Game의 기본 출력** 선택**복사본**합니다.  
  
13. 아래에서 바로 가기 메뉴를 열고는 **이름** 열에 **대상 컴퓨터의 파일**, 선택 **붙여넣기**합니다. 이라는 새 항목이 **Game.Primary Output** 나타납니다.  
  
14. **솔루션 탐색기**아래는 **응용 프로그램 데이터 지정** 노드를 열고는 **재배포 가능 요소** 페이지.  
  
15. 에 **재배포 가능 패키지 (Game Installer)** 편집기 창의 탭에에서는 **Visual c + + 11.0 CRT (x86)** 확인란 합니다.  
  
16. 메뉴 모음에서 **빌드**, **솔루션 빌드** 게임 프로젝트와 게임 설치 프로젝트를 빌드할 수 있습니다.  
  
17. 솔루션 폴더에서, 게임 설치 프로젝트에 내장된 setup.exe 프로그램을 찾아 실행 게임 응용 프로그램을 컴퓨터에 설치합니다. 이 파일을 복사하여 다른 컴퓨터에 응용 프로그램 및 기타 필요한 라이브러리 파일을 설치할 수 있습니다.  
  
18. 설치 프로젝트에서 요구 사항에 따라 다양한 옵션을 설정할 수 있습니다. 자세한 내용은 **솔루션 탐색기**아래에서 **Game Installer** 프로젝트, 열기는 **시작** 페이지 하 고 F1 키를 여 ISLE 도움말 라이브러리를 선택 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [연습: 프로젝트 (c + +) 디버깅](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)