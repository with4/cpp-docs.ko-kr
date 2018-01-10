---
title: "COM 인터페이스 (Visual c + +) 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.com.creating.interfaces
dev_langs: C++
helpviewer_keywords: COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7b5820686c3e6f01c37cbf527d0e631e5bcc25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-com-interface-visual-c"></a>COM 인터페이스 만들기(Visual C++)
Visual c + + COM 개체 및 자동화 클래스에 대 한 COM 정의 인터페이스 및 dispinterface를 사용 하는 프로젝트를 만드는 마법사 및 서식 파일을 제공 합니다.  
  
 다음과 같은 세 가지 일반적인 작업을 수행 하려면이 마법사를 사용할 수 있습니다.  
  
-   [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     사용 하 여 MFC 프로젝트를 만든 후 MFC 응용 프로그램에 대 한 ATL 지원 추가 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) 다음 실행 하 고는 **MFC에 ATL 지원 추가** 코드 마법사. 이 지원은 MFC 실행 파일 또는 DLL 프로젝트에 추가 하는 간단한 COM 개체에만 적용 됩니다. 이러한 ATL 개체에는 여러 인터페이스 있을 수 있습니다.  
  
-   [MFC ActiveX 컨트롤 만들기](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     열기는 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md) 는 dispinterface와는 event 맵이 각각.idl 파일 및 컨트롤 클래스에 정의 된 ActiveX 컨트롤을 만드는 데 합니다.  
  
-   [ATL 컨트롤 추가](../atl/reference/adding-an-atl-control.md)  
  
     조합을 사용 하 여는 [ATL 프로젝트 마법사](../atl/reference/atl-project-wizard.md) 및 [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md) ATL ActiveX 컨트롤을 만듭니다.  
  
     또한 위에서 설명한 것 처럼 ATL 지원 추가 MFC 프로젝트에 ATL 컨트롤을 추가할 수 있습니다. 또한 선택 하는 경우 **ATL 컨트롤** 에 **클래스 추가** 에 ATL 지원을 추가할 것인지 묻는 대화 상자를 표시 하는 Visual Studio, 대화 상자, ATL 지원을 MFC 프로젝트에 아직 추가 하지 않은 사용자 MFC 프로젝트입니다.  
  
     이 마법사는 프로젝트 클래스에서 IDL 소스 및 com을 생성합니다.  
  
 ATL 프로젝트를 열면, 있으면는 [클래스 추가](../ide/add-class-dialog-box.md) 대화 상자에서는 추가 마법사 및 서식 파일 프로젝트에 COM 인터페이스를 추가 하려면 선택 합니다. 다음 마법사를 사용 하는 개체에 대 한 하나 이상의 인터페이스를 설정할 수 있습니다.  
  
-   [ATL COM+ 1.0 구성 요소 마법사](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL Active Server Page 구성 요소 마법사](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL 컨트롤 마법사](../atl/reference/atl-control-wizard.md)  
  
 클래스 뷰에서 개체의 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 하 여 COM 컨트롤에 새 인터페이스를 구현할 수는 또한 [인터페이스 구현](../ide/implement-interface-wizard.md)합니다.  
  
> [!NOTE]
>  Visual Studio 프로젝트에는 인터페이스를 추가 하는 마법사를 제공 하지 않습니다. ATL 프로젝트 또는 인터페이스를 추가할 수는 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md) 사용 하 여 간단한 개체를 추가 하 여는 [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md)합니다. 또는 프로젝트의.idl 파일을 열고를 입력 하 여 인터페이스를 만듭니다.  
  
```  
interface IMyInterface {  
};  
  
```  
  
 참조 [인터페이스 구현](../ide/implementing-an-interface-visual-cpp.md) 및 [ATL 프로젝트에 추가 하는 개체 및 컨트롤](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) 자세한 정보에 대 한 합니다.  
  
 Visual c + +에서는 여러 가지 방법을 볼 및 [COM 인터페이스 편집](../ide/editing-a-com-interface.md) 프로젝트에 대해 정의 합니다. [클래스 뷰](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) dispinterface c + + 프로젝트에.idl 파일에 정의 된 또는 인터페이스에 대해 아이콘이 표시 됩니다.  
  
 클래스 뷰 ATL 기반 COM 개체 클래스에 대 한 ATL 클래스에서 구현 하는 모든 인터페이스와의 관계를 표시 하려면 ATL 클래스에서 COM 맵을 읽습니다.  
  
 클래스 뷰 및 바로 가기 메뉴에서 사용할 수 있습니다 인터페이스와 다음과 같습니다.  
  
-   MFC 기반 응용 프로그램에 ATL 개체를 추가 합니다.  
  
-   메서드, 속성 및 이벤트를 추가 합니다.  
  
-   항목을 두 번 클릭 하 여 항목의 인터페이스 코드에 직접 이동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 마법사를 사용 하 여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [코드 마법사로 기능 추가](../ide/adding-functionality-with-code-wizards-cpp.md)