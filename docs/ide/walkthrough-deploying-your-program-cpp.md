---
title: "연습: 프로그램 배포(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "응용 프로그램 배포[C++], 연습"
  - "설치 프로젝트[C++]"
  - "프로그램 배포[C++]"
  - "프로젝트[C++], 설치"
  - "프로젝트[C++], 프로그램 배포"
  - "응용 프로그램 배포[C++], 연습"
ms.assetid: 79e6cc4e-dced-419d-aaf7-d62d1367603f
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 프로그램 배포(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 기재된 초기 관련 연습을 수행하여 응용 프로그램을 만들었으므로 마지막 단계는 사용자가 컴퓨터에 프로그램을 설치할 수 있도록 설치 관리자를 만드는 것입니다.  이렇게 하려면 기존 솔루션에 새 프로젝트를 추가합니다.  이 새 프로젝트에서 다른 컴퓨터에 응용 프로그램을 설치하는 setup.exe 파일이 생성됩니다.  
  
 이 연습에서는 Windows Installer를 사용하여 응용 프로그램을 배포하는 방법을 보여 줍니다.  ClickOnce를 사용하여 응용 프로그램을 배포할 수도 있습니다.  자세한 내용은 [Visual C\+\+ 응용 프로그램의 ClickOnce 배포](../ide/clickonce-deployment-for-visual-cpp-applications.md)을 참조하십시오.  일반적인 배포에 대한 자세한 내용은 [응용 프로그램, 서비스 및 구성 요소 배포](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)를 참조하십시오.  
  
## 사전 요구 사항  
  
-   이 연습에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 기재된 초기 관련 연습을 수행해야 합니다.  
  
-   Visual Studio Express Edition에서는 이 연습을 수행할 수 없습니다.  
  
-   아직 연습을 수행하지 않았으면 이 문서 뒷부분의 설명에 따라 ISLE\(InstallShield Limited Edition\)를 다운로드합니다.  ISLE은 Visual Studio 개발자를 위한 무료 버전이며 이전 Visual Studio 버전의 설치 및 배포 프로젝트 템플릿 기능을 대체합니다.  
  
### ISLE 설치 및 배포 프로젝트 템플릿을 설치하려면  
  
1.  인터넷에 연결되어 있으면 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  대화 상자의 왼쪽 창에서 **설치됨**, **템플릿** 및 **기타 프로젝트 형식** 노드를 확장한 후 **설치 및 배포**를 선택합니다.  가운데 창에서 **InstallShield Limited Edition 사용**을 선택한 다음 **확인** 단추를 선택합니다.  
  
3.  지침을 따라 InstallShield Limited Edition for Visual Studio\(ISLE\)를 설치합니다.  
  
4.  ISLE를 다운로드, 설치 및 정품 인증한 후 Visual Studio를 닫았다가 다시 엽니다.  
  
5.  메뉴 모음에서 **파일**, **최근에 사용한 프로젝트 및 솔루션** 을 선택하고 **게임** 솔루션을 선택하여 다시 엽니다.  
  
### 설치 프로젝트를 만들고 프로그램을 설치하려면  
  
1.  활성 솔루션 구성을 릴리스로 변경합니다.  메뉴 모음에서 **빌드**, **구성 관리자**를 선택합니다.  **구성 관리자** 대화 상자의 **활성 솔루션 구성** 드롭다운 상자 목록에서 **릴리스**를 선택합니다.  **닫기** 단추를 선택하여 구성을 저장합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
3.  대화 상자의 왼쪽 창에서 **설치됨**, **템플릿** 및 **기타 프로젝트 형식** 노드를 확장한 후 **설치 및 배포**를 선택합니다.  가운데 창에서 **InstallShield Limited Edition 프로젝트**를 선택합니다.  
  
4.  **이름** 상자에 설치 프로젝트의 이름을 입력합니다.  이 예에서는 Game Installer를 입력합니다.  **솔루션** 드롭다운 목록에서 **솔루션에 추가**를 선택합니다.  **확인** 단추를 선택하여 설치 프로젝트를 만듭니다.  편집기 창에 **프로젝트 도우미\(게임 설치 관리자\)** 탭이 열립니다.  
  
5.  **프로젝트 도우미\(게임 설치 관리자\)** 탭 하단에서 **응용 프로그램 정보** 링크를 선택합니다.  
  
6.  **응용 프로그램 정보** 페이지에서 설치 프로그램에서 표시할 회사 이름을 지정합니다.  자신의 회사 이름을 사용할 수 있습니다. 이 예에서는 Contoso를 사용합니다.  응용 프로그램 이름을 지정합니다. 이 예제에서는 게임을 지정합니다.  회사 웹 사이트 주소를 지정합니다. 이 예제에서는 http:\/\/www.contoso.com을 사용합니다.  
  
7.  **프로젝트 도우미\(게임 설치 관리자\)** 탭 하단에서 **설치 인터뷰** 링크를 선택합니다.  
  
8.  **라이선스 계약 표시 대화 상자** 아래에 있는 **설치 인터뷰** 페이지에서 **아니요** 옵션 단추를 선택합니다.  **사용자에게 회사 이름과 사용자 이름을 입력하라는 메시지를 표시하시겠습니까?**에서 **아니요** 옵션 단추를 선택합니다.  
  
9. **솔루션 탐색기**에서 **Game Installer** 프로젝트, **Organize Your Setup** 노드를 차례로 확장한 후 **General Information** 페이지를 엽니다.  
  
10. 편집기 창에 있는 **General Information \(Game Installer\)** 탭에서 **태그 생성 ID**를 지정합니다\(예: regid.2012\-12.com.Contoso\).  
  
11. **솔루션 탐색기**의 **Game Installer** 프로젝트 아래에서 **Specify Application Data** 노드를 확장한 후 **Files** 페이지를 엽니다.  
  
12. **컴퓨터 소스 파일** 아래의 편집기 창에 있는 **Files \(Game Installer\)** 탭에서 **game의 기본 출력** 바로 가기 메뉴를 열고 **복사**를 선택합니다.  
  
13. **컴퓨터 대상 파일**의 **이름** 열 아래에서 바로 가기 메뉴를 열고 **붙여넣기**를 선택합니다.  **Game.Primary Output**이라는 새 항목이 나타납니다.  
  
14. **솔루션 탐색기**의 **응용 프로그램 데이터 지정** 노드에서 **재배포 가능 요소** 페이지를 엽니다.  
  
15. 편집기 창에 있는 **재배포 가능\(게임 설치 관리자\)** 탭에서 **11.0 CRT Visual C\+\+ \(x86\)** 확인란을 선택합니다.  
  
16. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택하여 게임 프로젝트와 게임 설치 프로젝트를 구성할 수 있습니다.  
  
17. 솔루션 폴더에서, 게임 설치 프로젝트에 내장된 setup.exe 프로그램을 찾아 실행 게임 응용 프로그램을 컴퓨터에 설치합니다.  이 파일을 복사하여 다른 컴퓨터에 응용 프로그램 및 기타 필요한 라이브러리 파일을 설치할 수 있습니다.  
  
18. 설치 프로젝트에서 요구 사항에 따라 다양한 옵션을 설정할 수 있습니다.  자세한 내용을 보려면 **솔루션 탐색기**의 **Game Installer** 프로젝트 아래에서 **시작** 페이지를 연 다음 F1 키를 선택하여 ISLE 도움말 라이브러리를 선택하십시오.  
  
## 다음 단계  
 **이전:** [연습: 프로젝트 디버깅\(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)