---
title: "클래스 추가(Visual C++) | Microsoft Docs"
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
  - "vc.codewiz.classes.adding"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL 프로젝트, 클래스 추가"
  - "클래스[C++], 추가"
  - "클래스[C++], 만들기"
ms.assetid: c34b5f70-4e72-4faa-ba21-e2b05361c4d9
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클래스 추가(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 프로젝트에서 클래스를 추가하려면 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음 **클래스**를 클릭합니다.  그러면 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md) 대화 상자가 열립니다.  
  
 클래스를 추가할 때는 MFC나 ATL에 이미 있는 클래스와는 다른 이름을 지정해야 합니다.  라이브러리에 이미 있는 이름을 지정하면 Visual C\+\+에서는 지정한 이름이 이미 예약되어 있음을 나타내는 메시지를 표시합니다.  
  
 프로젝트 명명 규칙에 따라 기존 이름을 사용해야 하는 경우 Visual C\+\+에서는 대\/소문자를 구분하므로 이름에서 하나 이상의 대\/소문자를 변경할 수 있습니다.  예를 들어 클래스 이름을 `CDocument`로 지정할 수 없더라도 `cdocument`로 지정할 수는 있습니다.  
  
## 추가할 클래스의 종류  
 **클래스 추가** 대화 상자에서 왼쪽 창의 **Visual C\+\+** 노드를 확장하면 설치된 템플릿의 여러 그룹화가 표시됩니다.  그룹에는 **CLR**, **ATL**, **MFC** 및 **C\+\+**가 포함됩니다.  그룹을 선택할 때 해당 그룹에서 사용 가능한 템플릿 목록이 가운데 창에 표시됩니다.  각 템플릿에는 클래스에 필요한 파일과 소스 코드가 포함됩니다.  
  
 새 클래스를 생성하려면 가운데 창에서 템플릿을 선택하고 **이름** 상자에 클래스 이름을 입력한 다음 **추가**를 클릭합니다.  그러면 클래스에 옵션을 지정할 수 있는 **클래스 추가 마법사**가 열립니다.  
  
-   MFC 클래스를 만드는 방법에 대한 자세한 내용은 [MFC 클래스](../mfc/reference/adding-an-mfc-class.md)를 참조하십시오.  
  
-   ATL 클래스를 만드는 방법에 대한 자세한 내용은 [ATL Simple Object](../atl/reference/adding-an-atl-simple-object.md)를 참조하십시오.  
  
> [!NOTE]
>  **MFC에 ATL 지원 추가** 템플릿은 클래스를 만들지 않고 대신 ATL을 사용하도록 프로젝트를 구성합니다.  자세한 내용은 [MFC 프로젝트의 ATL 지원](../mfc/reference/adding-atl-support-to-your-mfc-project.md)를 참조하십시오.  
  
 MFC, ATL 또는 CLR을 사용하지 않는 C\+\+ 클래스를 만들려면 설치된 템플릿의 **C\+\+** 그룹에서 **C\+\+ 클래스** 템플릿을 사용합니다.  자세한 내용은 [일반 C\+\+ 클래스 추가](../ide/adding-a-generic-cpp-class.md)를 참조하십시오.  
  
 두 가지 종류의 폼 기반 C\+\+ 클래스를 사용할 수 있습니다.  이 중 첫 번째 클래스인 [CFormView Class](../mfc/reference/cformview-class.md)는 MFC 클래스를 만들고  두 번째 클래스는 CLR Windows Forms 클래스를 만듭니다.  
  
## 참고 항목  
 [폼 기반 MFC 응용 프로그램 만들기](../mfc/reference/creating-a-forms-based-mfc-application.md)   
 [클래스 추가 대화 상자](../ide/add-class-dialog-box.md)   
 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)