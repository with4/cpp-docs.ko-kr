---
title: "MFC 클래스 추가 마법사 | Microsoft Docs"
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
  - "vc.codewiz.class.mfc.simple.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 클래스 추가 마법사"
  - "마법사[MFC]"
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC 클래스 추가 마법사
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 코드 마법사를 사용하여 기존 MFC 프로젝트에 클래스를 추가하거나 MFC를 지원하는 ATL 프로젝트에 클래스를 추가합니다.  또한 MFC를 지원하는 Win32 프로젝트에 MFC 클래스를 추가할 수도 있습니다.  프로젝트를 만들 때 지정한 기능에 따라 이 대화 상자에서 사용할 수 있는 옵션이 결정됩니다.  
  
## 이름  
 이 페이지에서는 클래스 이름, 기본 클래스 및 새 클래스의 파일 이름을 지정합니다.  
  
 **클래스 이름**  
 새 클래스 이름을 지정하고 이 페이지의 ID 및 파일 이름에 사용할 기본 텍스트를 입력합니다.  일반적으로 C\+\+ 클래스는 "C"로 시작하므로 "CMyClass"의 경우 "MyClass.h"가 됩니다.  
  
 **기본 클래스**  
 새 클래스의 기본 클래스 이름을 지정합니다.  기본적으로 기본 클래스는 [CWnd](../../mfc/reference/cwnd-class.md)입니다.  선택한 기본 클래스에 따라 이 페이지의 다른 상자가 활성화될지 여부가 결정됩니다.  
  
 기본 클래스로 설정한 클래스 형식에 따라 대화 상자 ID와 리소스 ID 중 어떤 것이 클래스에 포함될지 여부가 결정됩니다.  클래스의 일반 형식은 다음과 같습니다.  
  
-   [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md) 또는 [CDocument](../../mfc/reference/cdocument-class.md)와 같은 클래스에는 대화 상자 ID나 리소스 ID가 필요하지 않습니다.  이러한 클래스는 대화 상자 ID나 리소스 ID를 사용하지 않습니다.  기본 클래스로 이러한 클래스 중 하나를 선택하면 **대화 상자 ID** 상자와 **DHTML 리소스 ID** 상자가 흐리게 표시됩니다.  
  
-   [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md) 또는 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)와 같은 클래스에는 대화 상자 ID가 필요합니다.  
  
-   [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 클래스에는 대화 상자 ID, DHTML 리소스 ID 및 HTML 파일 이름이 필요합니다.  
  
 대화 상자 ID가 필요한 클래스의 경우, [리소스 편집기](../../mfc/resource-editors.md)를 사용하여 대화 상자 리소스를 만들고 [속성 창](../Topic/Properties%20Window.md)에서 해당 ID를 할당한 다음 해당 리소스 ID와 관련된 클래스를 만드는 것이 더 효율적입니다.  표준 Windows 대화 상자를 만드는 방법에 대한 자세한 내용은 [새 대화 상자 만들기](../../mfc/creating-a-new-dialog-box.md)를 참조하십시오.  
  
> [!NOTE]
>  대화 상자 리소스를 먼저 만든 다음 `CDHtmlDialog`에서 새 클래스를 파생시킨 경우 기본 대화 상자에 나타나는 표준 Windows **확인** 단추와 **취소** 단추를 삭제하십시오.  표준 Windows 대화 상자에서는 DHTML 폼을 호스팅하는데, 이 폼에는 자체의 **확인** 단추와 **취소** 단추가 포함되어 있습니다.  
  
 대화 상자에 Windows 컨트롤과 DHTML 컨트롤을 모두 포함시킬 수 있지만 권장되지 않습니다.  
  
 **대화 상자 ID**  
 `CDialog`, `CFormView`, `CPropertyPage` 또는 `CDHtmlDialog`를 **기본 클래스**로 선택한 경우 대화 상자의 ID를 지정합니다.  
  
 **.h 파일**  
 새 개체 클래스의 헤더 파일 이름을 설정합니다.  기본적으로 이 이름은 **클래스 이름**에 입력한 이름을 기본으로 합니다.  원하는 위치에 파일 이름을 저장하거나 기존 파일에 클래스 선언을 추가하려면 줄임표\(...\) 단추를 클릭합니다.  기존 파일을 선택하면 마법사에서 **마침**을 클릭할 때까지 선택한 위치에 파일이 저장되지 않습니다.  
  
 또한 마법사에서는 파일을 덮어쓰지 않습니다.  기존 파일 이름을 선택한 경우 **마침**을 클릭하면 파일 내용에 클래스 선언을 추가할 것인지 묻는 메시지가 나타납니다.  파일을 추가하려면 **예**를 클릭하고, 마법사로 돌아가서 다른 파일 이름을 지정하려면 **아니요**를 클릭합니다.  
  
 **.cpp 파일**  
 새 개체 클래스의 구현 파일 이름을 설정합니다.  기본적으로 이 이름은 **클래스 이름**에 입력한 이름을 기본으로 합니다.  원하는 위치에 파일 이름을 저장하려면 줄임표\(...\) 단추를 클릭합니다.  마법사에서 **마침**을 클릭할 때까지 선택한 위치에 파일이 저장되지 않습니다.  
  
 또한 마법사에서는 파일을 덮어쓰지 않습니다.  기존 파일 이름을 선택한 경우 **마침**을 클릭하면 파일 내용에 클래스 구현을 추가할 것인지 묻는 메시지가 나타납니다.  파일을 추가하려면 **예**를 클릭하고, 마법사로 돌아가서 다른 파일 이름을 지정하려면 **아니요**를 클릭합니다.  
  
 **Active Accessibility**  
 생성자에서 [EnableActiveAccessibility](../Topic/CWnd::EnableActiveAccessibility.md)를 호출하여 Active Accessibility에 대한 MFC 지원을 활성화합니다.  이 옵션은 [CWnd](../../mfc/reference/cwnd-class.md)에서 파생된 클래스에 사용할 수 있습니다.  
  
 **DHTML 리소스 ID**  
 이 옵션은 `CDHtmlDialog`에서 파생된 클래스에만 적용되며,  DHTML 대화 상자의 리소스 ID를 지정합니다.  프로젝트 .rc 파일의 HTML 섹션에 HTML 대화 상자 파일 이름과 함께 리소스 ID가 표시됩니다.  이 ID로 식별되는 DHTML 리소스는 **대화 상자 ID**로 식별되는 대화 상자에 호스팅됩니다.  
  
 **.HTM 파일**  
 이 옵션은 `CDHtmlDialog`에서 파생된 클래스에만 적용되며,  DHTML 대화 상자에 대한 HTML 파일 이름을 설정합니다.  기본적으로 이 파일 이름은 클래스 이름을 기본으로 합니다.  프로젝트 .rc 파일의 HTML 섹션에 DHTML 대화 상자 리소스 ID와 함께 해당 파일 이름이 표시됩니다.  
  
 **자동화**  
 [자동화](../../mfc/automation.md)에 대한 클래스 수준의 지원을 설정합니다.  클래스 수준의 자동화는 자동화를 지원하는 모든 클래스에 사용할 수 있습니다.  자동화 지원을 사용하여 만든 프로젝트에도 사용할 수 있습니다.  [ATL을 지원하는](../../atl/reference/mfc-support-in-atl-projects.md) MFC 프로젝트 또는 MFC 응용 프로그램 마법사의 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) 페이지에서 **자동화** 확인란을 선택한 MFC 프로젝트입니다.  
  
|옵션|설명|  
|--------|--------|  
|**없음**|클래스에서 자동화를 지원하지 않음을 나타냅니다.|  
|**자동화**|클래스에서 자동화를 지원함을 나타냅니다.  이 옵션을 선택한 경우 새로 만든 클래스는 Microsoft Visual Basic이나 Microsoft Excel과 같은 자동화 클라이언트 응용 프로그램에서 프로그래밍 가능한 개체로 사용할 수 있습니다.  이 표 다음에 제공되는 기본 클래스에는 이 옵션을 사용할 수 없습니다.|  
|**형식 ID로 생성 가능\(E\)**|클래스와 프로젝트 모두에서 자동화를 사용하여 이 클래스의 개체를 만드는 다른 응용 프로그램을 지원함을 나타냅니다.  이 옵션을 사용하면 자동화 클라이언트에서 직접 자동화 개체를 만들 수 있습니다.  클라이언트 응용 프로그램에서는 만들려는 개체를 지정할 때 이 입력란의 형식 ID를 사용합니다. 이 형식 ID는 시스템 전반적인 것으로 고유해야 합니다.  이 표 다음에 제공되는 기본 클래스에는 이 옵션을 사용할 수 없습니다.|  
  
 다음 기본 클래스에는 자동화 지원을 사용할 수 없습니다.  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **형식 ID**  
 클래스의 형식 ID를 설정합니다.  The **Type ID** box concatenates the project name and the new class name as follows: *MFCProj.MFCClass*.  **자동화** 옵션 **형식 ID로 생성 가능**을 선택한 경우에만 이 ID를 변경할 수 있습니다.  
  
 **DocTemplate 리소스 생성**  
 응용 프로그램에서 만든 문서에 문서 템플릿 리소스가 있음을 나타냅니다.  이 확인란을 활성화하려면 프로젝트에서 MFC 문서\/뷰 아키텍처를 지원해야 하며 이 클래스의 기본 클래스는 [CFormView](../../mfc/reference/cformview-class.md)여야 합니다.  
  
 자세한 내용은 [문서 템플릿과 문서\/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)를 참조하십시오.  
  
## 참고 항목  
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)