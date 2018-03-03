---
title: "(C + +) 코드 마법사로 기능 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes
dev_langs:
- C++
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c27aeb10a58c828b6503ce96ddaadf138c258f27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-functionality-with-code-wizards-c"></a>(C + +) 코드 마법사로 기능 추가
프로젝트를 만든 후 변경 하거나 해당 프로젝트의 기능을 추가 합니다. 이러한 작업에는 새 멤버 함수 및 변수 및 추가 자동화 메서드 및 속성을 추가 하는 새 클래스 만들기. 코드 마법사는 이러한 작업 모두 수행 하기 위한 것입니다.  
  
> [!NOTE]
>  이제 추가 메시지 처리기 및 메시지를 매핑할 및 MFC를 사용 하는 가상 함수를 재정의 [속성 창](/visualstudio/ide/reference/properties-window)합니다.  
  
## <a name="accessing-visual-c-code-wizards"></a>Visual c + + 코드 마법사에 액세스  
 다음 위치에서 Visual c + + 코드 마법사를 액세스할 수 있습니다.  
  
-   에 **프로젝트** 메뉴는 **새 항목 추가** 명령 (를) 실행 하는 할 수 있습니다는 `Add New Item` 대화 상자가 있습니다. **클래스 추가** 명령 표시는 [클래스 추가](../ide/add-class-dialog-box.md) 클래스의 각 형식에 대 한 마법사를 다시 열고 대화 상자에서 프로젝트에 추가할 수 있습니다. **리소스 추가** 명령 표시는 [리소스 추가](../windows/add-resource-dialog-box.md) 만들 하거나 프로젝트에 추가할 리소스 선택 수 있는 대화 상자.  
  
     클래스 뷰에서 프로젝트는 클래스 또는 인터페이스를 선택 하는 경우는 **프로젝트** 메뉴 다음 명령이 표시 됩니다.  
  
    -   **인터페이스를 구현** (에서 컨트롤 클래스에만 해당)  
  
    -   **Add 함수**  
  
    -   **변수 추가**  
  
    -   **연결 지점 추가** (ATL 클래스에만 해당)  
  
    -   **Add 메서드** (에서 인터페이스에만 해당)  
  
    -   **속성 추가** (에서 인터페이스에만 해당)  
  
    -   **이벤트 추가** (에서 컨트롤 클래스에만 해당)  
  
-   **솔루션 탐색기**모든 폴더를 마우스 오른쪽 단추로 클릭 하 고 클릭 하 **추가** 는 바로 가기에서 메뉴 새로운 또는 기존 파일, 더 많은 폴더, 항목, 클래스, 리소스를 추가할 수 있습니다 및 웹에 대 한 참조는 프로젝트입니다.  
  
-   [클래스 뷰 창을](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)적합 한 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 하면 **추가** 는 바로 가기에서 메뉴 함수, 변수, 클래스, 속성, 메서드, 이벤트, 인터페이스, 추가할 수 있습니다 연결 지점 또는 기타 코드 프로젝트에 있습니다.  
  
    > [!NOTE]
    >  Visual Studio 프로젝트에는 인터페이스를 추가 하는 마법사를 제공 하지 않습니다. ATL 프로젝트 또는 인터페이스를 추가할 수는 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md) 사용 하 여 간단한 개체를 추가 하 여는 [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)합니다. 또는 프로젝트의.idl 파일을 열고를 입력 하 여 인터페이스를 만듭니다.  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     참조 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md) 및 [ATL 프로젝트에 추가 하는 개체 및 컨트롤](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) 자세한 정보에 대 한 합니다.  
  
    |코드 마법사 액세스|설명|  
    |-----------------------------|-----------------|  
    |새 항목 추가|새 항목 추가 코드 마법사는 프로젝트에 소스 파일을 추가 합니다. 필요한 경우 추가 디렉터리를 기다리며 프로젝트 빌드 엔진에서는 해당 위치는 파일을 포함 하도록 생성 됩니다. 항목 추가 아이콘에서 사용할 수 있는 코드 마법사는 다음과 같습니다.<br /><br /> -C + + 소스 파일 (.cpp,.h,.idl,.rc,.srf,.def,.rgs)를 추가 합니다.<br />-웹 개발 파일 (.html,.asp,.css,.xml)를 추가 합니다.<br />-유틸리티 및 리소스 파일 (.bmp,.cur,.ico,.rct,.sql,.txt)을 추가 합니다.<br /><br /> 이러한 코드 마법사는 일반적으로 한 정보를 요청 하지 않습니다 하지만 개발 트리에 파일을 추가 합니다. 속성 창에서 파일 이름을 바꿀 수 있습니다.|  
    |솔루션 탐색기|솔루션 탐색기에서 사용할 수 있는 코드 마법사 항목을 마우스 오른쪽 단추로 클릭할 때 커서가 위치에 따라 달라 집니다. 경우는 **추가** 개발 트리에서 한 수준 위로 커서를 이동한 다음 항목을 마우스 오른쪽 단추로 클릭할 때 옵션이 표시 되지 않고 하 고 다시 시도 하십시오. 코드 마법사는 항상 추가 코드를 배치 개발 트리에서 해당 위치에 관계 없이 커서입니다. 솔루션 탐색기에서 사용할 수 있는 코드 마법사는 다음과 같습니다.<br /><br /> --클래스를 추가 하는 중 (열립니다는 **클래스 추가** 새 코드 마법사를 포함 하는 대화 상자).<br />--리소스를 추가 하는 중 (새로 만들기, 가져오기, 또는 사용자 지정).<br />-웹 참조를 추가 합니다.|  
    |클래스 뷰|코드 마법사 클래스 뷰에서 사용할 수 있는 항목을 마우스 오른쪽 단추로 클릭할 때 커서가 위치에 따라 달라 집니다. 경우는 **추가** 클래스 트리에서 한 수준 위로 커서를 이동한 다음 항목을 마우스 오른쪽 단추로 클릭할 때 옵션이 표시 되지 않고 하 고 다시 시도 하십시오. 코드 마법사는 항상 추가 코드를 배치 개발 트리에서 해당 위치에 관계 없이 커서입니다. 클래스 뷰에서 사용할 수 있는 코드 마법사는 다음과 같습니다.<br /><br /> -   [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)합니다.<br />-   [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)합니다.<br />-   [클래스 추가](../ide/adding-a-class-visual-cpp.md)합니다.<br />-   [인터페이스를 구현](../ide/implement-interface-wizard.md) (에서 컨트롤 클래스에만 해당)<br />-   [연결 지점 추가](../ide/implement-connection-point-wizard.md) (ATL 클래스에만 해당)<br />-   [Add 메서드](../ide/add-method-wizard.md) (에서 인터페이스에만 해당)<br />-   [속성 추가](../ide/names-add-property-wizard.md) (에서 인터페이스에만 해당)<br />-   [이벤트 추가](../ide/add-event-wizard.md) (에서 컨트롤 클래스에만 해당)<br /><br /> 클래스 추가 선택 열립니다는 **클래스 추가** 모든 새 클래스 추가 코드 마법사에 액세스할 수 있는 대화 상자.|  
  
## <a name="see-also"></a>참고 항목  
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)   
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual c + + 프로젝트 형식](../ide/visual-cpp-project-types.md)   
 [Visual C++ 프로젝트용 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)