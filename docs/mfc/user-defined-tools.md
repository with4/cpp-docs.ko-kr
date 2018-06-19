---
title: 사용자 정의 도구 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a3b755fc35c98652ab87231e9d8f58cde748bfc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384350"
---
# <a name="user-defined-tools"></a>사용자 정의 형식
MFC는 사용자 지정 도구를 지원합니다. 사용자 정의 도구는 외부 사용자가 지정한 프로그램을 실행 하는 특별 한 명령입니다. 사용자 정의 도구를 관리 하려면 사용자 지정 프로세스를 사용할 수 있습니다. 그러나 응용 프로그램 개체에서 파생 되지 않은 경우이 과정을 사용할 수 없습니다 [CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)합니다. 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [MFC에 대 한 사용자 지정](../mfc/customization-for-mfc.md)합니다.  
  
 사용자 지정 대화 상자에 자동으로 지원 되는 사용자 지정 도구를 사용 하는 경우는 **도구** 탭 합니다. 다음 그림에서는 **도구** 페이지.  
  
 ![사용자 지정 대화 상자의 도구 탭](../mfc/media/custdialogboxtoolstab.png "custdialogboxtoolstab")  
사용자 지정 대화 상자 도구 탭  
  
## <a name="enabling-user-defined-tools-support"></a>지원 도구 사용자 지정을 사용 하도록 설정  
 응용 프로그램에서 사용자 정의 도구를 사용 하려면 호출 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools)합니다. 그러나 먼저 여러 상수가이 호출에 대 한 매개 변수로 사용 하도록 응용 프로그램의 리소스 파일에 정의 해야 합니다.  
  
 리소스 편집기에서 적절 한 명령 ID를 사용 하는 더미 명령 만들기 다음 예제에서는 사용 하 여 **ID_TOOLS_ENTRY** 로 명령 id입니다. 이 명령은 ID 프레임 워크는 사용자 지정 도구를 삽입 하는 하나 이상의 메뉴에서 위치를 표시 합니다.  
  
 해야 따로 설정한 일부 연속 Id 사용자 지정 도구를 나타내도록 문자열 테이블에 있습니다. 따로 설정 하는 문자열의 수는 사용자 도구는 사용자가 정의할 수 있는 최대 수와 같습니다. 다음 예제에서는 행 그룹의 이름은 **ID_USER_TOOL1** 통해 **ID_USER_TOOL10**합니다.  
  
 제안 사항, 사용자가 도구와 디렉터리와 호출 되는 외부 프로그램에 대 한 인수를 선택 하는 데 도움이 하도록 제안할 수 있습니다. 이 작업을 수행 하려면 리소스 편집기에서 두 개의 팝업 메뉴를 만듭니다. 다음 예제에서 행 그룹의 이름은 **IDR_MENU_ARGS** 및 **IDR_MENU_DIRS**합니다. 이러한 메뉴에 있는 각 명령에 대 한 응용 프로그램 문자열 테이블에는 문자열을 정의 합니다. 문자열의 리소스 ID는 명령 id입니다. 동일 해야 합니다.  
  
 파생된 된 클래스를 만들 수도 있습니다 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 기본 구현은 교체할 수 있습니다. 이렇게 하려면 파생 된 클래스에 대 한 런타임 정보 RUNTIME_CLASS 대신 CWinAppEx::EnableUserTools에서 네 번째 매개 변수로 전달 합니다 ([CUserTool 클래스](../mfc/reference/cusertool-class.md)).  
  
 적절 한 상수를 정의 하면 호출 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) 사용자 정의 도구를 사용 하도록 합니다.  
  
 다음 메서드 호출이 이러한 상수를 사용 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]  
  
 이 예제에서는 도구 탭에 포함 됩니다는 **사용자 지정** 대화 상자. 프레임 워크 명령 ID와 일치 하는 모든 명령 바뀝니다 **ID_TOOLS_ENTRY** 사용자가 해당 메뉴를 열 때마다 현재 정의 된 사용자 도구 집합이 포함 된 모든 메뉴에 있습니다. 명령 Id **ID_USER_TOOL1** 통해 **ID_USER_TOOL10** 사용자 정의 도구에 대 한 사용 하도록 예약 합니다. 클래스 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 사용자 도구에 대 한 호출을 처리 합니다. 도구 탭은 **사용자 지정** 대화 상자는 메뉴에 액세스 하려면 인수 및 directory 입력 필드의 오른쪽에는 단추를 제공 **IDR_MENU_ARGS** 및 **IDR_MENU_DIRS**. 사용자가 이러한 메뉴 중 하나에서 명령으로 선택할 때 프레임 워크가 추가 적절 한 텍스트 상자에 같은 명령 id와 같습니다. 리소스 ID를 가진 문자열  
  
### <a name="including-predefined-tools"></a>미리 정의 된 도구를 포함 하 여  
 일부 도구는 응용 프로그램 시작 시에 미리 정의 하려는 경우 재정의 해야는 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 응용 프로그램의 주 창의 메서드. 해당 메서드를 다음 단계를 수행 해야 합니다.  
  
##### <a name="to-add-new-tools-in-loadframe"></a>LoadFrame의 새로운 도구를 추가 하려면  
  
1.  한 포인터를 가져옵니다는 [CUserToolsManager 클래스](../mfc/reference/cusertoolsmanager-class.md) 호출 하 여 개체 [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager)합니다.  
  
2.  만들려고 할 수 있는 모든 도구에 대 한 호출 [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool)합니다. 이 메서드가 반환에 대 한 포인터는 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 개체를 새로 만든된 사용자 도구 tools의 내부 컬렉션에 추가 합니다. 파생된 클래스에 대 한 런타임 정보를 제공 하는 경우 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 의 네 번째 매개 변수로 [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) 인스턴스화하고 대신 해당 클래스의 인스턴스를 반환 합니다.  
  
3.  각 도구에 대해 설정 하 여 해당 텍스트 레이블을 설정 `CUserTool::m_strLabel` 해당 명령을 호출 하 여 설정 하 고 `CUserTool::SetCommand`합니다. 기본 구현은 [CUserTool 클래스](../mfc/reference/cusertool-class.md) 호출에 지정 된 프로그램에서 사용 가능한 아이콘을 자동으로 검색 `SetCommand`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC에 대 한 사용자 지정](../mfc/customization-for-mfc.md)   
 [CUserTool 클래스](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager 클래스](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx 클래스](../mfc/reference/cwinappex-class.md)




