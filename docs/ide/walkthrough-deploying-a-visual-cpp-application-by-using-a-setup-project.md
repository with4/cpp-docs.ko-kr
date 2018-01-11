---
title: "설치 프로젝트를 사용 하 여 Visual c + + 응용 프로그램 배포 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: deployment for Visual C++
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fbe75f1fd3ceb037e44716156556882f3f6d1cc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-deploying-a-visual-c-application-by-using-a-setup-project"></a>연습: 설치 프로젝트를 사용하여 Visual C++ 응용 프로그램 배포
설치 프로젝트를 Visual c + + 응용 프로그램 배포를 사용 하는 방법을 설명 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   사용 하는 컴퓨터 [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] 설치 합니다.  
  
-   Visual c + + 라이브러리를 하지 않은 추가 컴퓨터  
  
### <a name="to-deploy-an-application-by-using-a-setup-project"></a>설치 프로젝트를 사용 하 여 응용 프로그램을 배포 하려면  
  
1.  사용 하 여는 **MFC ApplicationWizard** 새 Visual Studio 솔루션을 만들려면 합니다. 마법사에서 찾을 수는 **새 프로젝트** 대화 상자에서 **Visual c + +** 노드를 선택 **MFC**선택, **MFC 응용 프로그램**를 입력 한 프로젝트에 대 한 이름을 지정 하 고 클릭 **확인**합니다.  
  
2.  활성 솔루션 구성을 변경 **릴리스**합니다. **빌드** 메뉴 선택 **Configuration Manger**합니다. **Configuration Manager** 대화 상자에서 **릴리스** 에서 **활성 솔루션 구성** 드롭다운 상자입니다.  
  
3.  응용 프로그램을 빌드하려면 F7 키를 누릅니다. 는 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다. 그러면이 MFC 응용 프로그램 프로젝트의 출력을 사용 하도록 설치 프로젝트.  
  
4.  그렇게 이미 하지 않은 경우 InstallShield Limited Edition ISLE (), Visual Studio 개발자를 위한 무료 이며 설치 및 배포에 대 한 Visual Studio에서 프로젝트 템플릿 기능을 대체 하는 다운로드 합니다. 인터넷에 연결한 경우에 열에서 **새 프로젝트** 대화 상자를 선택 하 여 **파일**, **새로**, **프로젝트** 메뉴 또는 도구 모음에서 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택한 **추가**, **새 프로젝트**합니다. 확장 된 **기타 프로젝트 형식** 노드를 선택 **InstallShield Limited Edition** 에 **설치 및 배포** 노드를 표시 되는 지침을 따릅니다. 다운로드 하 고, 설치 하 고, InstallShield Limited Edition을 활성화 했으면, Visual Studio를 닫고 다시 엽니다.  
  
5.  열기는 **새 프로젝트** 대화 상자를 다시 확장 하 고는 **기타 프로젝트 형식** 노드를 선택 하 고 **InstallShield Limited Edition 프로젝트** 에  **InstallShield Limited Edition** 노드.  
  
6.  지침에 따라는 **시작** InstallShield Limited Edition 서식 파일을 Visual Studio MFC 프로젝트 출력 참조를 추가 하 여 만든 설치 프로젝트의 노드.  
  
7.  설치 관리자 파일 (setup.exe)을 만드는 설치 프로젝트를 빌드하십시오. 설치 프로젝트 노드를 마우스 오른쪽 단추로 클릭이 위해 **솔루션 탐색기** 선택 **빌드**합니다.  
  
     InstallShield Limited Edition 설치 프로젝트 트리에서 설치 파일을 만듭니다 (기본적으로이 위치할 수는 설치 프로젝트의 Express\SingleImage\DiskImages\DISK1 하위 폴더에).  
  
8.  Visual c + + 라이브러리를 하지 않은 두 번째 컴퓨터에 설치 프로그램을 실행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [배포 예제](../ide/deployment-examples.md)