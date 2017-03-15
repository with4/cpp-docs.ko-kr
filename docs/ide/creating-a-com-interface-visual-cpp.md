---
title: "COM 인터페이스 만들기(Visual C++) | Microsoft Docs"
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
  - "vc.codewiz.com.creating.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM 인터페이스, 만들기"
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM 인터페이스 만들기(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 COM 개체와 자동화 클래스에 대해 인터페이스 및 dispinterface를 정의하는 COM 사용 프로젝트를 만들기 위한 마법사와 템플릿을 제공합니다.  
  
 이 마법사에서는 다음과 같은 일반적인 세 가지 작업을 수행할 수 있습니다.  
  
-   [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용한 다음 **MFC에 ATL 지원 추가** 코드 마법사를 실행하여 MFC 프로젝트를 만든 후에 MFC 응용 프로그램에 ATL 지원을 추가합니다.  이 지원은 MFC 실행 파일이나 DLL 프로젝트에 추가된 단순 COM 개체에만 적용됩니다.  이 ATL 개체에는 여러 인터페이스가 있을 수 있습니다.  
  
-   [MFC ActiveX 컨트롤 만들기](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)를 열어 .idl 파일과 컨트롤 클래스에 각각 정의되어 있는 dispinterface와 이벤트 맵으로 ActiveX 컨트롤을 만듭니다.  
  
-   [ATL 컨트롤 추가](../atl/reference/adding-an-atl-control.md)  
  
     [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md)와 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)를 함께 사용하여 ATL ActiveX 컨트롤을 만듭니다.  
  
     위에서 설명한 대로 ATL 지원을 추가한 MFC 프로젝트에 ATL 컨트롤을 추가할 수도 있습니다.  또한, **클래스 추가** 대화 상자에서 **ATL 컨트롤**을 선택하고 MFC 프로젝트에 ATL 지원을 아직 추가하지 않은 경우 MFC 프로젝트에 ATL 지원을 추가할 것인지 묻는 대화 상자가 나타납니다.  
  
     이 마법사에서는 프로젝트 클래스에 IDL 소스와 COM 맵을 생성합니다.  
  
 ATL 프로젝트를 열면 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자에서 프로젝트에 COM 인터페이스를 추가하기 위한 다른 마법사와 템플릿을 선택할 수 있습니다.  다음 마법사를 사용하면 개체에 하나 이상의 인터페이스를 설정할 수 있습니다.  
  
-   [ATL COM\+ 1.0 구성 요소 마법사](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL Active Server Page 구성 요소 마법사](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)  
  
 또한 클래스 뷰에서 개체의 컨트롤 클래스를 마우스 오른쪽 단추로 클릭한 다음 [인터페이스 구현](../ide/implement-interface-wizard.md)을 클릭하여 COM 컨트롤에 새 인터페이스를 구현할 수 있습니다.  
  
> [!NOTE]
>  Visual Studio에서는 프로젝트에 인터페이스를 추가하는 데 사용할 수 있는 마법사를 제공하지 않습니다.  [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)를 사용하여 단순 개체를 추가하는 방법으로 ATL 프로젝트에 인터페이스를 추가하거나 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)할 수 있습니다.  또는 프로젝트의 .idl 파일을 열고 다음과 같이 입력하여 인터페이스를 만들 수 있습니다.  
  
```  
interface IMyInterface {  
};  
  
```  
  
 자세한 내용은 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md) 및 [ATL 프로젝트에 개체 및 컨트롤 추가](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)를 참조하십시오.  
  
 Visual C\+\+에서는 프로젝트에 정의된 [COM 인터페이스를 편집](../ide/editing-a-com-interface.md)할 수 있는 몇 가지 방법을 제공합니다.  [클래스 뷰](http://msdn.microsoft.com/ko-kr/8d7430a9-3e33-454c-a9e1-a85e3d2db925)에서는 C\+\+ 프로젝트의 .idl 파일에 정의된 인터페이스 또는 dispinterface에 대한 아이콘을 표시합니다.  
  
 ATL 기반 COM 개체 클래스의 경우 클래스 뷰에서는 ATL 클래스의 COM 맵을 읽고 ATL 클래스와 ATL 클래스에서 구현하는 모든 인터페이스 간의 관계를 표시합니다.  
  
 클래스 뷰와 해당하는 바로 가기 메뉴에서 다음과 같이 인터페이스로 작업할 수 있습니다.  
  
-   ATL 개체를 MFC 기반 응용 프로그램에 추가할 수 있습니다.  
  
-   메서드, 속성 및 이벤트를 추가할 수 있습니다.  
  
-   항목을 두 번 클릭하여 항목의 인터페이스 코드로 바로 이동할 수 있습니다.  
  
## 참고 항목  
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)