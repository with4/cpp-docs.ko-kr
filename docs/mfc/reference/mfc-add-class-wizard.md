---
title: MFC 클래스 추가 마법사 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9560dec12a7710076f752d5329269c844f0d3a8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373413"
---
# <a name="mfc-add-class-wizard"></a>MFC 클래스 추가 마법사
이 코드 마법사를 사용 하 여 기존 MFC 프로젝트에 클래스를 추가 또는 MFC를 지 원하는 ATL 프로젝트에 클래스를 추가 합니다. 또한 MFC 지원을 지 Win32 프로젝트를 MFC 클래스를 추가할 수 있습니다. 프로젝트를 만들 때 지정한 기능이 대화 상자에서 사용할 수 있는 옵션을 결정 합니다.  
  
## <a name="names"></a>이름  
 이 페이지에서 클래스 이름, 기본 클래스 및 새 클래스에 대 한 파일 이름을 지정 합니다.  
  
 **클래스 이름**  
 새 클래스의 이름을 지정 하 고의 Id 및이 페이지에는 파일 이름에 대 한 기본 텍스트를 제공 합니다. 일반적으로 c + + 클래스 예를 들어 "CMyClass"가 "MyClass.h", "C"로 시작 합니다.  
  
 **기본 클래스**  
 새 클래스에 대 한 기본 클래스의 이름을 지정합니다. 기본적으로 기본 클래스는 [CWnd](../../mfc/reference/cwnd-class.md)합니다. 선택한 기본 클래스의 다른 상자가이 페이지에 활성화 되어 있는지 여부를 결정 합니다.  
  
 기본 클래스를 클래스에는 대화 ID 또는 id가 리소스 ID가 있는지 여부를 결정 하는 대로 설정 하는 클래스의 유형 클래스의 일반적인 종류는 다음과 같습니다.  
  
-   와 같은 클래스 [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), 또는 [CDocument](../../mfc/reference/cdocument-class.md), 대화 상자가 필요 하지 않은 ID 또는 리소스 id입니다. 이러한 클래스는 대화 상자 또는 리소스 ID를 사용 하지 않습니다. 기본 클래스에 대 한 이러한 클래스 중 하나를 선택 하는 경우는 **대화 ID** 상자 및 **DHTML 리소스 ID** 상자 흐리게 표시 됩니다.  
  
-   와 같은 클래스 [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), 또는 [CPropertyPage](../../mfc/reference/cpropertypage-class.md), 필요한는 대화 id입니다.  
  
-   클래스 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), 대화 상자 ID, DHTML 리소스 ID 및 HTML 파일 이름이 필요 합니다.  
  
 대화 ID를 필요로 하는 클래스에 대 한 있습니다는 것이 더 효율적 사용 하는 [리소스 편집기](../../windows/resource-editors.md) 대화 상자 리소스를 만들려면 해당 ID에서 할당할는 [속성 창](/visualstudio/ide/reference/properties-window)를 만든 후 관련 된 클래스 리소스 ID를 가진 참조 [새 대화 상자 만들기](../../windows/creating-a-new-dialog-box.md) 표준 Windows 대화 상자를 만드는 방법에 대 한 자세한 내용은 합니다.  
  
> [!NOTE]
>  새 클래스를 파생을 먼저 대화 상자 리소스를 만든 경우 `CDHtmlDialog`, 표준 Windows 삭제 **확인** 및 **취소** 기본 대화 상자에 표시 되는 단추입니다. 표준 Windows 대화 상자를 자체 포함 된 DHTML 양식 호스트 **확인** 및 **취소** 단추입니다.  
  
 대화 상자에는 Windows 컨트롤 및 DHTML 컨트롤 둘 다 포함 될 수 있습니다, 동안 권장 되지 않습니다.  
  
 **대화 상자 ID**  
 선택한 경우에 대화의 ID를 지정 `CDialog`, `CFormView`, `CPropertyPage`, 또는 `CDHtmlDialog` 로 **기본 클래스**합니다.  
  
 **.h 파일**  
 새 개체의 클래스에 대 한 헤더 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **클래스 이름**합니다. 사용자가 선택한 위치에 파일 이름을 저장 하거나 기존 파일을 클래스 선언을 추가 하려면 줄임표 단추를 클릭 합니다. 기존 파일을 선택 하면 마법사 파일이 저장 되지 것입니다 선택한 위치에 할 때까지 클릭 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 선택한 경우 기존 파일의 이름을 클릭 하면 **마침**, 클래스 선언 파일의 내용을 추가 해야 할지 여부를 묻는 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **.cpp 파일**  
 새 개체의 클래스에 대 한 구현 파일의 이름을 설정합니다. 기본적으로이 이름은에서 제공 하는 이름에 따라 **클래스 이름**합니다. 파일 이름을 원하는 위치에 저장 하려면 줄임표 단추를 클릭 합니다. 파일을 클릭할 때까지 선택한 위치에 저장 되지 않습니다 **마침** 마법사에서.  
  
 마법사는 파일을 덮어쓰지 않습니다. 경우 클릭할 때 기존 파일의 이름을 선택 **마침**, 마법사에서 클래스에 구현 파일의 내용에 추가할 것인지 여부를 묻는 메시지를 표시 합니다. 클릭 **예** ; 파일을 추가 클릭 **아니요** 하 고 마법사로 돌아갑니다 하 고 다른 파일 이름을 지정 합니다.  
  
 **Active accessibility**  
 호출 하 여 Active Accessibility에 대 한 MFC의 지원을 가능 [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) 생성자에서 합니다. 파생 된 클래스에이 옵션은 사용할 [CWnd](../../mfc/reference/cwnd-class.md)합니다.  
  
 **DHTML 리소스 ID**  
 파생 된 클래스에 적용 됩니다 `CDHtmlDialog` 만 합니다. DHTML 대화 상자의 리소스 ID를 지정합니다. 리소스 ID HTML 대화 상자 파일 이름과 함께 프로젝트의.rc 파일의 HTML 섹션에 표시 됩니다. 로 식별 되는 대화 상자에이 id는 DHTML 리소스는 호스팅됩니다 **대화 ID**합니다.  
  
 **. HTM 파일**  
 파생 된 클래스에 적용 됩니다 `CDHtmlDialog` 만 합니다. DHTML 대화 상자에 대 한 HTML 파일의 이름을 설정합니다. 기본적으로이 파일 이름은 클래스 이름에 기반 합니다. 파일 이름은 DHTML 대화 상자 리소스 id는 프로젝트의.rc 파일의 HTML 섹션에 표시  
  
 **자동화**  
 설정에 대 한 지원의 클래스 수준 [자동화](../../mfc/automation.md)합니다. 자동화 클래스 수준에서 자동화를 지 원하는 모든 클래스에 대해 ´ ù. 자동화를 지 원하는 사용 하 여 만든 프로젝트에 사용할 수 이기도 합니다. 즉, 중 하나는 MFC 프로젝트에 [ATL 지원](../../atl/reference/mfc-support-in-atl-projects.md), 또는 선택 된 MFC 프로젝트는 **자동화** 확인란에는 [고급 기능](../../mfc/reference/advanced-features-mfc-application-wizard.md) MFC의 페이지 응용 프로그램 마법사입니다.  
  
|옵션|설명|  
|------------|-----------------|  
|**없음**|클래스가 자동화를 지원 하지에 있음을 나타냅니다.|  
|**자동화**|클래스가 자동화를 지원함을 나타냅니다. 이 옵션을 선택 하는 경우 새로 만든된 클래스는 Microsoft Visual Basic 및 Microsoft Excel과 같은 자동화 클라이언트 응용 프로그램에서 프로그래밍 가능한 개체 수 있습니다. 이 옵션은이 테이블 다음에 나열 된 기본 클래스에 사용할 수 없습니다.|  
|**유형 ID로 생성 가능**|클래스와 프로젝트에는 자동화를 사용 하 여이 클래스의 개체를 만드는 다른 응용 프로그램을 지원 나타냅니다. 자동화 클라이언트는이 옵션을 사용 자동화 개체를 직접 만들 수 있습니다. 유형 ID 텍스트 상자에 만들; 개체를 지정 하는 클라이언트 응용 프로그램이 사용 됩니다. 시스템 수준 되며 고유 해야 합니다. 이 옵션은이 테이블 다음에 나열 된 기본 클래스에 사용할 수 없습니다.|  
  
 다음 기본 클래스에 대 한 자동화 지원 되지 않습니다.  
  
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
  
 **유형 ID**  
 클래스의 유형 ID를 설정합니다. **유형 ID** 상자 프로젝트 이름 및 새 클래스 이름을 연결 다음과 같이: *MFCProj.MFCClass*합니다. 이 ID를 선택한 경우에 변경할 수는 **자동화** 옵션 **유형 ID로 생성 가능**합니다.  
  
 **DocTemplate 리소스 생성**  
 문서 템플릿 리소스가 응용 프로그램에서 만든 문서 했음을 나타냅니다. 이 확인란을 활성화 하려면 프로젝트에는 MFC 문서/뷰 아키텍처를 지원 해야 하며이 클래스의 기본 클래스 여야 [CFormView](../../mfc/reference/cformview-class.md)합니다.  
  
 참조 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 클래스](../../mfc/reference/adding-an-mfc-class.md)   
 [클래스 추가](../../ide/adding-a-class-visual-cpp.md)
