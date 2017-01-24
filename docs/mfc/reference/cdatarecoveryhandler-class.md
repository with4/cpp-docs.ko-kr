---
title: "CDataRecoveryHandler Class | Microsoft Docs"
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
  - "CDataRecoveryHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataRecoveryHandler class"
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataRecoveryHandler Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDataRecoveryHandler` Autosaves 문서 및 응용 프로그램이 예기치 않게 종료 될 경우이 복원 합니다.  
  
## 구문  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## Members  
  
### 생성자  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](../Topic/CDataRecoveryHandler::CDataRecoveryHandler.md)|`CDataRecoveryHandler` 개체를 생성합니다.|  
  
### 메서드  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveAllDocumentInfo.md)|각 파일을 등록 하 여 Autosaves의 `CDataRecoveryHandler` 클래스입니다.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveDocumentInfo.md)|지정한 문서의 Autosaves입니다.|  
|[CDataRecoveryHandler::CreateDocumentInfo](../Topic/CDataRecoveryHandler::CreateDocumentInfo.md)|문서 열기 문서 목록에 추가합니다.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](../Topic/CDataRecoveryHandler::DeleteAllAutosavedFiles.md)|현재 자동 저장 됨 파일을 모두 삭제합니다.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](../Topic/CDataRecoveryHandler::DeleteAutosavedFile.md)|지정한 자동 저장 됨 파일을 삭제합니다.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](../Topic/CDataRecoveryHandler::GenerateAutosaveFileName.md)|제공 된 문서 파일 이름에 연결 된 자동 저장 파일 이름을 생성 합니다.|  
|[CDataRecoveryHandler::GetAutosaveInterval](../Topic/CDataRecoveryHandler::GetAutosaveInterval.md)|자동 저장 시도 사이의 간격을 반환합니다.|  
|[CDataRecoveryHandler::GetAutosavePath](../Topic/CDataRecoveryHandler::GetAutosavePath.md)|자동 저장 됨 파일의 경로 반환합니다.|  
|[CDataRecoveryHandler::GetDocumentListName](../Topic/CDataRecoveryHandler::GetDocumentListName.md)|문서 이름을 검색 하는 `CDocument` 개체입니다.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](../Topic/CDataRecoveryHandler::GetNormalDocumentTitle.md)|지정 된 문서에 대 한 기본 제목을 검색합니다.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](../Topic/CDataRecoveryHandler::GetRecoveredDocumentTitle.md)|만들고 복구 된 문서의 제목을 반환 합니다.|  
|[CDataRecoveryHandler::GetRestartIdentifier](../Topic/CDataRecoveryHandler::GetRestartIdentifier.md)|응용 프로그램에 대 한 고유 다시 시작 식별자를 검색합니다.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle.md)|표시 여부를 `CDataRecoveryHandler` 현재 유휴 루프에서 자동 저장을 수행 합니다.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](../Topic/CDataRecoveryHandler::GetShutdownByRestartManager.md)|다시 시작 관리자 응용 프로그램을 종료 하려면 발생 여부를 나타냅니다.|  
|[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md)|`CDataRecoveryHandler`를 초기화합니다.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::QueryRestoreAutosavedDocuments.md)|각 문서에 대화 상자를 표시 하는 `CDataRecoveryHandler` 자동 저장 됨.  대화 상자 사용자가 자동 저장 됨 문서 복원 하려는 여부를 결정 합니다.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](../Topic/CDataRecoveryHandler::ReadOpenDocumentList.md)|열려 있는 문서의 목록에서 레지스트리를 로드합니다.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](../Topic/CDataRecoveryHandler::RemoveDocumentInfo.md)|제공 된 문서 열기 문서 목록에서 제거합니다.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](../Topic/CDataRecoveryHandler::ReopenPreviousDocuments.md)|이전에 열려 있는 문서를 엽니다.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::RestoreAutosavedDocuments.md)|사용자 입력에 따라 자동 저장 됨 문서를 복원 합니다.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](../Topic/CDataRecoveryHandler::SaveOpenDocumentList.md)|현재 열려 있는 문서 목록을 Windows 레지스트리에 저장 됩니다.|  
|[CDataRecoveryHandler::SetAutosaveInterval](../Topic/CDataRecoveryHandler::SetAutosaveInterval.md)|자동 저장 주기를 밀리초에서 사이의 시간을 설정합니다.|  
|[CDataRecoveryHandler::SetAutosavePath](../Topic/CDataRecoveryHandler::SetAutosavePath.md)|디렉터리 파일 자동 저장 됨 저장 되는 위치를 설정 합니다.|  
|[CDataRecoveryHandler::SetRestartIdentifier](../Topic/CDataRecoveryHandler::SetRestartIdentifier.md)|고유 다시 식별자의이 인스턴스에 대해 설정 된 `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md)|설정 여부를 `CDataRecoveryHandler` 열려 있는 문서 정보를 Windows 레지스트리에 현재 유휴 주기 동안 저장 합니다.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](../Topic/CDataRecoveryHandler::SetShutdownByRestartManager.md)|다시 시작 관리자가 응용 프로그램의 이전 종료에 발생 한 여부를 설정 합니다.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](../Topic/CDataRecoveryHandler::UpdateDocumentInfo.md)|사용자가 저장 하기 때문에 문서에 대 한 정보를 업데이트 합니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|m\_bRestoringPreviousOpenDocs|데이터 복구 처리기 이전에 열려 있는 문서를 다시 열립니다 여부를 나타냅니다.|  
|m\_bSaveDocumentInfoOnIdle|데이터 복구 처리기 autosaves 유휴 루프에서 다음 문서 여부를 나타냅니다.|  
|m\_bShutdownByRestartManager|다시 시작 관리자 응용 프로그램 종료 되는지 여부를 나타냅니다.|  
|m\_dwRestartManagerSupportFlags|응용 프로그램에 대 한 내용 다시 시작 관리자 지원 나타내는 플래그를 제공 합니다.|  
|m\_lstAutosavesToDelete|원본 문서를 닫은 경우 삭제 된 자동 저장 됨 파일 목록이 있습니다.  때 응용 프로그램, 파일 삭제를 다시 시작 관리자 재시도 종료 됩니다.|  
|m\_mapDocNameToAutosaveName|자동 저장 됨 파일 이름으로 문서 이름이 맵.|  
|m\_mapDocNameToDocumentPtr|지도를 문서 이름에는  [CDocument](../../mfc/reference/cdocument-class.md) 포인터.|  
|m\_mapDocNameToRestoreBool|문서 자동 저장 됨 문서를 복원 하는지 여부를 나타내는 부울 매개 변수 이름의 맵.|  
|m\_mapDocumentPtrToDocName|지도 `CDocument` 문서 이름에 대 한 포인터입니다.|  
|m\_mapDocumentPtrToDocTitle|지도 `CDocument` 문서 제목에 대 한 포인터입니다.  이러한 제목 파일을 저장 하는 데 사용 됩니다.|  
|m\_nAutosaveInterval|Autosaves 사이의 밀리초 단위 시간입니다.|  
|m\_nTimerID|자동 저장 타이머에 대 한 식별자입니다.|  
|m\_strAutosavePath|문서 자동 저장 됨 저장 되는 위치를 위치입니다.|  
|m\_strRestartIdentifier|다시 시작 관리자에 대 한 GUID의 문자열 표현.|  
  
## 설명  
 다시 시작 관리자를 사용 하 여 `CDataRecoveryHandler` 클래스를 유지 하려면 추적 열려 있는 모든 문서를 자동 저장 하 여 필요에 따라.  자동 저장을 활성화 하려면 사용 하는 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md) 메서드.  이 메서드는 `CDataRecoveryHandler` 다음 유휴 루프에서 자동 저장을 수행 합니다.  다시 시작 관리자 호출 `SetSaveDocumentInfoOnIdle` 때의 `CDataRecoveryHandler` 에서 자동 저장을 수행 해야 합니다.  
  
 모든 방법 중에서 `CDataRecoveryHandler` 클래스는 가상.  사용자 고유의 사용자 지정 데이터 복구 처리기를 만들려면이 클래스의 메서드를 재정의 합니다.  데이터 복구 처리기를 직접 만들거나 관리자를 다시 시작 하지 않으면 Cdatarecoveryhandler를 인스턴스화할 수 없습니다.  [CWinApp Class](../../mfc/reference/cwinapp-class.md) 생성 한 `CDataRecoveryHandler` 필요에 따라 개체.  
  
 사용 하기 전에 `CDataRecoveryHandler` 개체를 호출 해야 [CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md).  
  
 때문에 `CDataRecoveryHandler` 클래스를 다시 시작 관리자에 밀접 하 게 연결 되어 `CDataRecoveryHandler` 글로벌 매개 변수에 따라 달라 집니다 `m_dwRestartManagerSupportFlags`.  이 매개 변수는 다시 시작 관리자 권한 및 응용 프로그램에 작용 하는 방식을 결정 합니다.  다시 시작 관리자는 기존 응용 프로그램에 통합 하려면 할당 된 `m_dwRestartManagerSupportFlags` 주 응용 프로그램의 생성자에서 적절 한 값입니다.  다시 시작 관리자를 사용 하는 방법에 대 한 자세한 내용은 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md).  
  
## 요구 사항  
 **헤더:** afxdatarecovery.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)