---
title: "코드 마법사로 기능 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클래스 마법사[C++]"
  - "코드 마법사[C++]"
  - "프로젝트[C++], 기능 추가"
  - "Visual C++ 프로젝트, 기능 추가"
  - "마법사[C++], 코드"
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 코드 마법사로 기능 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로젝트를 만들었으면 해당 프로젝트의 기능을 변경하거나 추가할 수 있습니다.  새 클래스 만들기, 새 멤버 함수 및 변수 추가, 자동화 메서드 및 속성 추가 등이 이러한 작업에 포함됩니다.  코드 마법사는 이러한 작업을 할 수 있도록 디자인된 것입니다.  
  
> [!NOTE]
>  이제 [속성 창](../Topic/Properties%20Window.md)을 사용하여 MFC 가상 함수를 재정의하고 메시지 처리기와 맵 메시지를 프로젝트에 추가할 수 있습니다.  
  
## Visual C\+\+ 코드 마법사 액세스  
 다음 위치에서 Visual C\+\+ 코드 마법사에 액세스할 수 있습니다.  
  
-   **프로젝트** 메뉴에서 **새 항목 추가** 명령을 사용하면 `Add New Item` 대화 상자가 나타납니다. 이 대화 상자에서 프로젝트에 새 파일을 추가할 수 있습니다.  **클래스 추가** 명령을 선택하면 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자가 표시된 다음 프로젝트에 추가할 수 있는 각 클래스 형식에 대한 마법사가 열립니다.  **리소스 추가** 명령을 선택하면 [리소스 추가](../windows/add-resource-dialog-box.md) 대화 상자가 나타납니다. 이 대화 상자에서 프로젝트에 추가할 리소스를 만들거나 선택할 수 있습니다.  
  
     클래스 뷰에서 프로젝트의 클래스나 인터페이스를 선택하면 **프로젝트** 메뉴에 다음 명령이 표시됩니다.  
  
    -   **인터페이스 구현**\(컨트롤 클래스에만 해당\)  
  
    -   **함수 추가**  
  
    -   **변수 추가**  
  
    -   **연결 지점 추가**\(ATL 클래스에만 해당\)  
  
    -   **메서드 추가**\(인터페이스에만 해당\)  
  
    -   **속성 추가**\(인터페이스에만 해당\)  
  
    -   **이벤트 추가**\(컨트롤 클래스에만 해당\)  
  
-   **솔루션 탐색기**에서 폴더를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **추가**를 클릭하면 새 파일이나 기존 파일, 추가 폴더, 항목, 클래스, 리소스, 웹 참조 등을 프로젝트에 추가할 수 있습니다.  
  
-   [클래스 뷰 창](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서 해당 노드를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **추가**를 클릭하면 함수, 변수, 클래스, 속성, 메서드, 이벤트, 인터페이스, 연결 지점 및 기타 코드를 프로젝트에 추가할 수 있습니다.  
  
    > [!NOTE]
    >  Visual Studio에서는 프로젝트에 인터페이스를 추가하는 데 사용할 수 있는 마법사를 제공하지 않습니다.  [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)를 사용하여 단순 개체를 추가하는 방법으로 ATL 프로젝트에 인터페이스를 추가하거나 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)할 수 있습니다.  또는 프로젝트의 .idl 파일을 열고 다음과 같이 입력하여 인터페이스를 만들 수 있습니다.  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     자세한 내용은 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md) 및 [ATL 프로젝트에 개체 및 컨트롤 추가](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)를 참조하십시오.  
  
    |코드 마법사 액세스|설명|  
    |----------------|--------|  
    |새 항목 추가|새 항목 추가 코드 마법사에서는 프로젝트에 소스 파일을 추가합니다.  필요한 경우, 해당 소스 파일을 포함할 추가 디렉터리가 만들어지며 프로젝트 빌드 엔진에서는 해당 디렉터리에서 소스 파일을 찾습니다.  항목 추가 아이콘에서 사용할 수 있는 코드 마법사에는 다음이 포함됩니다.<br /><br /> -   C\+\+ 소스 파일\(.cpp, .h, .idl, .rc, .srf, .def, .rgs\)을 추가합니다.<br />-   웹 개발 파일\(.html, .asp, .css, .xml\)을 추가합니다.<br />-   유틸리티 및 리소스 파일\(.bmp, .cur, .ico, .rct, .sql, .txt\)을 추가합니다.<br /><br /> 이 코드 마법사에서는 보통 정보를 요청하지 않고 개발 트리에 파일을 추가합니다.  속성 창에서 파일 이름을 변경할 수 있습니다.|  
    |솔루션 탐색기|항목을 마우스 오른쪽 단추로 클릭할 때 커서가 있는 위치에 따라 솔루션 탐색기에서 사용할 수 있는 코드 마법사가 달라집니다.  항목을 마우스 오른쪽 단추로 클릭할 때 **추가** 옵션이 나타나지 않으면 개발 트리에서 커서를 한 수준 위로 이동한 다음 다시 시도하십시오.  코드 마법사는 항상 커서 위치에 상관 없이 개발 트리의 해당 위치에 추가 코드를 배치합니다.  솔루션 탐색기에서 사용할 수 있는 코드 마법사는 다음과 같습니다.<br /><br /> -   클래스 추가\(새 코드 마법사를 포함하는 **클래스 추가** 대화 상자가 열림\)<br />-   리소스 추가\(새로 만들기, 가져오기 또는 사용자 지정\)<br />-   웹 참조 추가|  
    |클래스 뷰|항목을 마우스 오른쪽 단추로 클릭할 때 커서가 있는 위치에 따라 클래스 뷰에서 사용할 수 있는 코드 마법사가 달라집니다.  항목을 마우스 오른쪽 단추로 클릭할 때 **추가** 옵션이 나타나지 않으면 클래스 트리에서 커서를 한 수준 위로 이동한 다음 다시 시도하십시오.  코드 마법사는 항상 커서 위치에 상관 없이 개발 트리의 해당 위치에 추가 코드를 배치합니다.  클래스 뷰에서 사용할 수 있는 코드 마법사는 다음과 같습니다.<br /><br /> -   [멤버 함수 추가](../ide/adding-a-member-function-visual-cpp.md)<br />-   [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)<br />-   [클래스 추가](../ide/adding-a-class-visual-cpp.md)<br />-   [인터페이스 구현](../ide/implement-interface-wizard.md)\(컨트롤 클래스에만 해당\)<br />-   [연결 지점 추가](../ide/implement-connection-point-wizard.md)\(ATL 클래스에만 해당\)<br />-   [메서드 추가](../ide/add-method-wizard.md)\(인터페이스에만 해당\)<br />-   [속성 추가](../ide/names-add-property-wizard.md)\(인터페이스에만 해당\)<br />-   [이벤트 추가](../ide/add-event-wizard.md)\(컨트롤 클래스에만 해당\)<br /><br /> 클래스 추가를 선택하면 새로운 모든 **클래스 추가** 코드 마법사에 액세스할 수 있는 클래스 추가 대화 상자가 열립니다.|  
  
## 참고 항목  
 [가상 함수 재정의](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [클래스 구조 탐색](../ide/navigating-the-class-structure-visual-cpp.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C\+\+ 프로젝트 형식](../ide/visual-cpp-project-types.md)   
 [Visual C\+\+ 프로젝트용으로 만들어지는 파일 형식](../ide/file-types-created-for-visual-cpp-projects.md)