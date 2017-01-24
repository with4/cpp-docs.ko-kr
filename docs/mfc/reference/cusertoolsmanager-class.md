---
title: "CUserToolsManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUserToolsManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUserToolsManager class"
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUserToolsManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컬렉션을 유지 [CUserTool Class](../../mfc/reference/cusertool-class.md) 응용 프로그램에서.  사용자 도구 외부 응용 프로그램을 실행 하는 메뉴 항목입니다.  `CUserToolsManager` 개체를 사용자 또는 개발자가 응용 프로그램에 새 사용자 도구를 추가할 수 있습니다.  사용자 도구와 관련 된 명령이 실행을 지원 하 고 사용자 도구에 대 한 정보는 Windows 레지스트리를 저장 합니다.  
  
## 구문  
  
```  
class CUserToolsManager : public CObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CUserToolsManager::CUserToolsManager](../Topic/CUserToolsManager::CUserToolsManager.md)|`CUserToolsManager`를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md)|새 사용자 도구를 만듭니다.|  
|[CUserToolsManager::FindTool](../Topic/CUserToolsManager::FindTool.md)|반환에 대 한 포인터는 `CMFCUserTool` 지정 된 명령 ID와 연결 된 개체|  
|[CUserToolsManager::GetArgumentsMenuID](../Topic/CUserToolsManager::GetArgumentsMenuID.md)|관련 된 리소스 ID를 반환 합니다.는  **인수** 메뉴에는  **도구** 탭의  **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetDefExt](../Topic/CUserToolsManager::GetDefExt.md)|기본 확장명을 반환의  **파일 열기** 대화 상자 \([CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)\)에서 사용 하는  **명령** 필드에  **도구** 탭의는  **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetFilter](../Topic/CUserToolsManager::GetFilter.md)|파일 필터를 반환의  **파일 열기** 대화 상자 \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\)에서 사용 하는  **명령** 필드에  **도구** 탭의는  **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetInitialDirMenuID](../Topic/CUserToolsManager::GetInitialDirMenuID.md)|관련 된 리소스 ID를 반환 합니다.는  **초기 디렉터리** 메뉴에는  **도구** 탭의  **사용자 지정** 대화 상자.|  
|[CUserToolsManager::GetMaxTools](../Topic/CUserToolsManager::GetMaxTools.md)|사용자 도구에 할당할 수 있는 최대 응용 프로그램에 반환 합니다.|  
|[CUserToolsManager::GetToolsEntryCmd](../Topic/CUserToolsManager::GetToolsEntryCmd.md)|명령 ID의 사용자 도구에 대 한 메뉴 항목 자리 표시자를 반환합니다.|  
|[CUserToolsManager::GetUserTools](../Topic/CUserToolsManager::GetUserTools.md)|목록 사용자가 도구에 대 한 참조를 반환 합니다.|  
|[CUserToolsManager::InvokeTool](../Topic/CUserToolsManager::InvokeTool.md)|지정 된 명령 ID가 사용자 도구와 연결 된 응용 프로그램 실행|  
|[CUserToolsManager::IsUserToolCmd](../Topic/CUserToolsManager::IsUserToolCmd.md)|사용자 도구와 연결 된 명령 ID 인지 확인 합니다.|  
|[CUserToolsManager::LoadState](../Topic/CUserToolsManager::LoadState.md)|Windows 레지스트리에서 사용자 도구에 대 한 정보를 로드합니다.|  
|[CUserToolsManager::MoveToolDown](../Topic/CUserToolsManager::MoveToolDown.md)|지정 된 사용자 도구 사용자 도구 목록에서 아래로 이동합니다.|  
|[CUserToolsManager::MoveToolUp](../Topic/CUserToolsManager::MoveToolUp.md)|지정 된 사용자 도구 사용자 도구 목록에서 위로 이동 합니다.|  
|[CUserToolsManager::RemoveTool](../Topic/CUserToolsManager::RemoveTool.md)|응용 프로그램에서 지정 된 사용자 도구를 제거합니다.|  
|[CUserToolsManager::SaveState](../Topic/CUserToolsManager::SaveState.md)|사용자 도구에 대 한 정보는 Windows 레지스트리에 저장합니다.|  
|[CUserToolsManager::SetDefExt](../Topic/CUserToolsManager::SetDefExt.md)|기본 확장명을 지정 하는  **파일 열기** 대화 상자 \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\) 사용는  **명령** 필드에  **도구** 탭의는  **사용자 지정** 대화 상자.|  
|[CUserToolsManager::SetFilter](../Topic/CUserToolsManager::SetFilter.md)|파일을 필터링 하는  **파일 열기** 대화 상자 \([CFileDialog Class](../../mfc/reference/cfiledialog-class.md)\)에서 사용 하는  **명령** 필드에  **도구** 탭의는  **사용자 지정** 대화 상자.|  
  
## 설명  
 사용자 도구를 응용 프로그램에 통합 하려면 다음을 수행 해야 합니다.  
  
 1.  메뉴 항목과 연결 된 명령 ID 사용자 도구 메뉴 항목에 대 한 예약 합니다.  
  
 2.  순차적 명령 ID는 사용자 응용 프로그램을 정의할 수 있는 각 사용자 도구에 대 한 예약 합니다.  
  
 3.  호출는 [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) 메서드는 다음 매개 변수를 입력 하 고: 메뉴 명령 ID, 첫 번째 사용자 도구 명령 ID 및 마지막 사용자 도구 명령 ID  
  
 있어야 하나의 글로벌 `CUserToolsManager` 개체 당 응용 프로그램.  
  
 사용자 도구에 대 한 예제에서는 VisualStudioDemo 예제 프로젝트를 참조 하십시오.  
  
## 예제  
 다음 참조를 검색 하는 예제는 `CUserToolsManager` 개체 및 새 사용자 도구를 만드는 방법.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#38](../../mfc/codesnippet/CPP/cusertoolsmanager-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxusertoolsmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [CUserTool Class](../../mfc/reference/cusertool-class.md)