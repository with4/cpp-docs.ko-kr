---
title: "COM 인터페이스 편집 | Microsoft Docs"
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
  - "vc.codewiz.com.editing.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM 인터페이스, 편집"
  - "메서드[C++], COM 인터페이스에 추가"
  - "속성[C++], COM 인터페이스에 추가"
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM 인터페이스 편집
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

클래스 뷰 바로 가기 메뉴의 명령을 사용하여 Visual C\+\+ 프로젝트의 COM 인터페이스에 대해 메서드와 속성을 새로 정의할 수 있습니다.  또한 도구 상자에서 ActiveX 컨트롤의 이벤트를 정의할 수 있습니다.  
  
 ATL 기반 COM 개체 클래스와 MFC 기반 COM 개체 클래스의 경우 인터페이스를 편집할 때 클래스 구현을 편집할 수 있습니다.  
  
> [!NOTE]
>  **클래스 추가** 대화 상자 외부에서 정의한 인터페이스의 경우, 인터페이스가 수동으로 추가된 경우에도 Visual C\+\+에서는 .idl 파일에 메서드나 속성을 추가하고, 메서드를 구현하는 클래스에 스텁을 추가합니다.  
  
 다음의 세 가지 마법사를 사용하면 기존의 인터페이스를 사용자 지정할 수 있습니다.  이러한 마법사는 클래스 뷰에서 사용할 수 있습니다.  
  
|마법사|프로젝트 형식|  
|---------|-------------|  
|[속성 추가 마법사](../ide/names-add-property-wizard.md)|ATL을 지원하는 ATL 프로젝트나 MFC 프로젝트에 사용합니다.  속성을 추가할 인터페이스를 마우스 오른쪽 단추로 클릭합니다.<br /><br /> Visual C\+\+에서는 프로젝트 형식을 검색하고 그 결과에 따라 속성 추가 마법사의 옵션을 수정합니다.<br /><br /> -   [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용하여 만든 프로젝트의 dispinterface의 경우 속성 추가 마법사를 호출하면 MFC에 관련된 옵션이 제공됩니다.<br />-   MFC ActiveX 컨트롤 인터페이스의 경우 속성 추가 마법사에서는 제공된 그대로 사용하거나 컨트롤에 맞게 사용자 지정할 수 있는 스톡 메서드 및 속성 목록을 제공합니다.<br />-   다른 모든 인터페이스의 경우 속성 추가 마법사에서는 대부분의 경우에 사용할 수 있는 옵션이 제공됩니다.|  
|[메서드 추가 마법사](../ide/add-method-wizard.md)|ATL을 지원하는 ATL 프로젝트나 MFC 프로젝트에 사용합니다.  메서드를 추가할 인터페이스를 마우스 오른쪽 단추로 클릭합니다.<br /><br /> Visual C\+\+에서는 프로젝트 형식을 검색하고 그 결과에 따라 메서드 추가 마법사의 옵션을 수정합니다.<br /><br /> -   [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)를 사용하여 만든 프로젝트의 dispinterface의 경우 메서드 추가 마법사를 호출하면 MFC에 관련된 옵션이 제공됩니다.<br />-   MFC ActiveX 컨트롤 인터페이스의 경우 메서드 추가 마법사에서는 제공된 그대로 사용하거나 컨트롤에 맞게 사용자 지정할 수 있는 스톡 메서드 및 속성 목록을 제공합니다.<br />-   다른 모든 인터페이스의 경우 **메서드 추가** 마법사에서는 대부분의 경우에 사용할 수 있는 옵션이 제공됩니다.|  
  
 또한 클래스 뷰에서 개체의 컨트롤 클래스를 마우스 오른쪽 단추로 클릭한 다음 [인터페이스 구현](../ide/implement-interface-wizard.md)을 클릭하여 COM 컨트롤에 새 인터페이스를 구현할 수 있습니다.  
  
## 참고 항목  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C\+\+ 프로젝트 형식](../ide/visual-cpp-project-types.md)