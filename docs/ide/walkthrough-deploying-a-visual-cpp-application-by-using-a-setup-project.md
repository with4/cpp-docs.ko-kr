---
title: "연습: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "Visual C++ 배포"
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설치 프로젝트를 사용하여 Visual C\+\+ 응용 프로그램을 배포하는 방법을 설명합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)]이 설치된 컴퓨터입니다.  
  
-   Visual C\+\+ 라이브러리가 없는 추가 컴퓨터  
  
### 설치 프로젝트를 사용하여 응용 프로그램을 배포하려면  
  
1.  **MFC 응용 프로그램 마법사**를 사용하여 새 Visual Studio 솔루션을 만듭니다.  이 마법사를 찾으려면 **새 프로젝트** 대화 상자에서 **Visual C\+\+** 노드를 확장하고 **MFC**, **MFC 응용 프로그램**을 차례로 선택한 다음 프로젝트 이름을 입력하고 **확인**을 클릭합니다.  
  
2.  활성 솔루션 구성을 **릴리스**로 변경합니다.  **빌드** 메뉴에서 **구성 관리자**를 선택합니다.  **구성 관리자** 대화 상자의 **활성 솔루션 구성** 드롭다운 상자에서 **릴리스**를 선택합니다.  
  
3.  F7 키를 눌러 응용 프로그램을 빌드합니다.  또는 **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  이 설치 프로젝트를이 MFC 응용 프로그램 프로젝트의 출력을 사용할 수 있습니다.  
  
4.  아직 수행 하지 않은 경우 InstallShield 제한 된 에디션 \(Visual Studio 개발자를 위한 무료 이며 기능을 Visual Studio 프로젝트 템플릿 설치 및 배포에 대 한 대체 눈물\)를 다운로드 합니다.  인터넷에 연결 되 면 열은  **새 프로젝트** 선택 대화 상자  **파일**,  **새**,  **프로젝트** 에서 솔루션을 마우스 오른쪽 단추로 클릭 하거나 메뉴 표시줄에서  **솔루션 탐색기** 선택 하 고  **추가**,  **새 프로젝트...**.  확장은  **기타 프로젝트 형식** 노드를 선택  **InstallShield 제한 된 에디션 사용** 에  **설치 및 배포** 노드를 클릭 하 고 나타나는 지시를 따릅니다.  다운로드 하 고 설치 하 고 제한 된 에디션 InstallShield 활성화 되 면 Visual Studio 닫고 다시 엽니다.  
  
5.  열기는  **새 프로젝트** 대화 상자 다시 확장은  **기타 프로젝트 형식** 노드를 선택 하 고  **InstallShield 제한 된 에디션 프로젝트** 에  **InstallShield 제한 된 에디션** 노드.  
  
6.  지침에  **시작** InstallShield 제한 된 에디션 템플릿을 MFC Visual Studio 프로젝트에 출력 참조를 추가 하 여 만든 설치 프로젝트의 노드.  
  
7.  설치 관리자 파일 \(setup.exe\)을 만드는 설치 프로젝트를 빌드하십시오.  이렇게 하려면 마우스 오른쪽 단추로 설치 프로젝트 노드를 클릭  **솔루션 탐색기** 을 선택 하 고  **빌드**.  
  
     제한 된 에디션 InstallShield 설치 프로젝트 트리에서 설치 파일을 만듭니다 \(기본적으로이 설치 프로젝트의 Express\\SingleImage\\DiskImages\\DISK1 하위 폴더에 있을 수 있습니다\).  
  
8.  Visual C\+\+ 라이브러리가 없는 두 번째 컴퓨터에서 설치 프로그램을 실행 합니다.  
  
## 참고 항목  
 [배포 예제](../ide/deployment-examples.md)