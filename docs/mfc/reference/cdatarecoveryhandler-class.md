---
title: CDataRecoveryHandler 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
dev_langs:
- C++
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ba9615f583069ec63946fe52840dc5bc4fa545e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376465"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler 클래스
`CDataRecoveryHandler` 문서화 하 고 응용 프로그램이 예기치 않게 종료 하는 경우 복원 하는 자동으로 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|`CDataRecoveryHandler` 개체를 생성합니다.|  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|각 파일에 등록 하는 자동으로 저장 된 `CDataRecoveryHandler` 클래스입니다.|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|지정된 된 문서에 자동으로 저장 합니다.|  
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|열린 문서 목록에 문서를 추가합니다.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|현재 자동 저장 된 파일을 모두 삭제 합니다.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|지정한 자동 저장 된 파일을 삭제합니다.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|제공된 문서 파일 이름에 연결 된 자동 저장 파일 이름을 생성 합니다.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|자동 저장 시도 사이의 간격을 반환합니다.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|자동 저장 된 파일의 경로 반환합니다.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|문서 이름을 검색 한 `CDocument` 개체입니다.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|지정된 된 문서에 대 한 일반 제목을 검색합니다.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|만들고 복구 된 문서에 대 한 title을 반환 합니다.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 대해 자동 저장을 수행 합니다.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|다시 시작 관리자 인해 응용 프로그램을 종료 하는지 여부를 나타냅니다.|  
|[CDataRecoveryHandler::Initialize](#initialize)|`CDataRecoveryHandler` 을(를) 초기화합니다.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|사용자에 게 대화 상자를 표시 하는 각 문서는 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하는 사용자가 있는지 여부를 결정 합니다.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|레지스트리에서 열려 있는 문서 목록을 로드합니다.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|열린 문서 목록에서 제공된 된 문서를 제거합니다.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|이전에 열려 있는 문서를 엽니다.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|사용자 입력에 따라 자동 저장 된 문서를 복원 합니다.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|밀리초 단위로 자동 저장 주기 사이의 시간을 설정 합니다.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|이 인스턴스에 대 한 고유 다시 시작 식별자를 설정 하는 `CDataRecoveryHandler`합니다.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|설정 여부는 `CDataRecoveryHandler` 현재 유휴 주기 동안 Windows 레지스트리에 열려 있는 문서 정보를 저장 합니다.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|다시 시작 관리자에 의해 발생 한 응용 프로그램의 이전 종료 여부를 설정 합니다.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|사용자를 저장 하기 때문에 문서에 대 한 정보를 업데이트 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|데이터 복구 처리기가 이전에 열린 문서가 있는지 여부를 나타냅니다.|  
|m_bSaveDocumentInfoOnIdle|다음 유휴 루프에 데이터 복구 처리기에서 문서 있는지 여부를 나타냅니다.|  
|m_bShutdownByRestartManager|다시 시작 관리자 응용 프로그램을 종료 하면 되는지를 나타냅니다.|  
|m_dwRestartManagerSupportFlags|응용 프로그램에 대 한 다시 시작 관리자 지원 기능을 나타내는 플래그를 제공 합니다.|  
|m_lstAutosavesToDelete|목록 삭제 되지 않는 원본 문서를 닫은 자동 저장 된 파일입니다. 응용 프로그램이 끝날 때 다시 시작 관리자 재시도 파일을 삭제 합니다.|  
|m_mapDocNameToAutosaveName|자동 저장 된 파일 이름으로 문서 이름 맵.|  
|m_mapDocNameToDocumentPtr|문서 이름으로 이루어진 지도 [CDocument](../../mfc/reference/cdocument-class.md) 포인터입니다.|  
|m_mapDocNameToRestoreBool|자동 저장 된 문서를 복원할지를 나타내는 부울 매개 변수를 문서 이름 맵.|  
|m_mapDocumentPtrToDocName|맵을 여 `CDocument` 문서 이름에 대 한 포인터입니다.|  
|m_mapDocumentPtrToDocTitle|지도 `CDocument` 문서 제목에 대 한 포인터입니다. 이러한 타이틀 파일 저장에 사용 됩니다.|  
|m_nAutosaveInterval|자동으로 저장 사이의 밀리초의 시간입니다.|  
|m_nTimerID|자동 저장 타이머에 대 한 식별자입니다.|  
|m_strAutosavePath|자동 저장 된 문서를 저장할 위치입니다.|  
|m_strRestartIdentifier|다시 시작 관리자에 대 한 GUID의 문자열 표현입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 다시 시작 관리자는 `CDataRecoveryHandler` 유지 하는 클래스를 추적 열려 있는 모든 문서 및 자동 저장을 필요에 따라 합니다. 자동 저장을 사용 하려면는 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) 메서드. 지시 하는이 메서드는 `CDataRecoveryHandler` 다음 유휴 루프에서 자동 저장을 수행할 수 있습니다. 다시 시작 관리자 호출 `SetSaveDocumentInfoOnIdle` 때는 `CDataRecoveryHandler` 자동 저장을 수행 해야 합니다.  
  
 메서드 중 일부는 `CDataRecoveryHandler` 클래스는 가상입니다. 사용자 고유의 사용자 지정 데이터 복구 처리기를 만들려면이 클래스의 메서드를 재정의 합니다. 사용자 고유의 데이터 복구 처리기를 만들거나 관리자 다시 시작 하지 않는 한는 CDataRecoveryHandler 인스턴스화하지 않습니다. [CWinApp 클래스](../../mfc/reference/cwinapp-class.md) 만듭니다는 `CDataRecoveryHandler` 필요 없게 되는 개체입니다.  
  
 사용 하기 전에 `CDataRecoveryHandler` 개체를 호출 해야 [CDataRecoveryHandler::Initialize](#initialize)합니다.  
  
 때문에 `CDataRecoveryHandler` 클래스를 다시 시작 관리자 밀접 하 게 연결할 `CDataRecoveryHandler` 글로벌 매개 변수에 따라 달라 집니다 `m_dwRestartManagerSupportFlags`합니다. 이 매개 변수는 다시 시작 관리자가 권한 및 응용 프로그램과 상호 작용 하는 방법을 결정 합니다. 기존 응용 프로그램에 다시 시작 관리자 통합할를 할당 해야 `m_dwRestartManagerSupportFlags` 주 응용 프로그램의 생성자에 적절 한 값입니다. 다시 시작 관리자를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>  CDataRecoveryHandler::AutosaveAllDocumentInfo  
 각 파일에 등록 하는 자동으로 저장 된 `CDataRecoveryHandler` 클래스입니다.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 경우는 `CDataRecoveryHandler` ; 모든 문서 저장 `FALSE` 경우 모든 문서 저장 되지 않았습니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 반환 `TRUE` 저장 해야 하는 문서가 없는 경우. 또한 반환 `TRUE` 검색 하는 경우 모든 문서를 저장 하지 않고는 `CWinApp` 또는 `CDocManager` 응용 프로그램에서 오류를 생성 합니다.  
  
 이 메서드를 하거나 사용 하려면 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 참조 [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) 자세한 정보에 대 한 합니다.  
  
##  <a name="autosavedocumentinfo"></a>  CDataRecoveryHandler::AutosaveDocumentInfo  
 지정된 된 문서에 자동으로 저장 합니다.  
  
```  
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,  
    BOOL bResetModifiedFlag = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|에 대 한 포인터는 `CDocument` 저장 합니다.|  
|[in] `bResetModifiedFlag`|`TRUE` 나타냅니다는 `CDataRecoveryHandler` 고려 `pDocument` 를 수정할 수 있습니다. `FALSE` 프레임 워크에서으로 간주 나타냅니다 `pDocument` 수정 됩니다. 이 플래그의 영향에 대 한 자세한 내용은 설명 섹션을 참조 하십시오.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 적절 한 플래그가 설정 된 경우 및 `pDocument` 유효한 `CDocument` 개체입니다.  
  
### <a name="remarks"></a>설명  
 각 `CDocument` 개체에 마지막으로 저장 한 이후 변경 되었는지 여부를 나타내는 플래그입니다. 사용 하 여 [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) 이 플래그의 상태를 결정 합니다. 경우는 `CDocument` 마지막 저장 한 이후 변경 되지 않은 `AutosaveDocumentInfo` 해당 문서에 대 한 모든 자동 저장 된 파일을 삭제 합니다. 문서의 마지막 저장 후 변경 된 경우 닫기 하 라는 메시지 닫기 전에 문서를 저장 합니다.  
  
> [!NOTE]
>  사용 하 여 `bResetModifiedFlag` 에 수정 되지 않은 문서 상태를 변경 하려면 저장 되지 않은 데이터 손실 발생할 수 있습니다. 프레임 워크에서 수정 되지 않은 문서를 닫기 표시 하지 않습니다는 사용자가을 저장할.  
  
 사용 하 여 예외를 throw 하는이 메서드는 [ASSERT](diagnostic-services.md#assert) 매크로 경우 `pDocument` 유효 하지 않거나 `CDocument` 개체입니다.  
  
 이 메서드를 하거나 사용 하려면 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="cdatarecoveryhandler"></a>  CDataRecoveryHandler::CDataRecoveryHandler  
 `CDataRecoveryHandler` 개체를 생성합니다.  
  
```  
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,  
    int nAutosaveInterval);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `dwRestartManagerSupportFlags`|다시 시작 관리자의 옵션에서 지원 되는지 나타냅니다.|  
|[in] `nAutosaveInterval`|자동으로 저장 사이의 시간입니다. 이 매개 변수는 밀리초에서입니다.|  
  
### <a name="remarks"></a>설명  
 MFC 프레임 워크에서 자동으로 만듭니다는 `CDataRecoveryHandler` 사용 하는 경우 응용 프로그램에 대 한 개체는 **새 프로젝트** 마법사. 데이터 복구 동작 또는 다시 시작 관리자를 사용자 지정 하려는 경우가 아니면 만들지 마십시오는 `CDataRecoveryHandler` 개체입니다.  
  
  
##  <a name="createdocumentinfo"></a>  CDataRecoveryHandler::CreateDocumentInfo  
 열린 문서 목록에 문서를 추가합니다.  
  
```  
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|에 대 한 포인터는 `CDocument`합니다. 이 메서드는이 문서 정보 만듭니다 `CDocument`합니다.|  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 `TRUE`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 확인 하는 경우 `pDocument` 문서를 추가 하기 전에 문서의 목록에 이미입니다. 경우 `pDocument` 과 연결 된 자동 저장 된 파일 삭제가이 메서드는 목록에 이미이 `pDocument`합니다.  
  
 이 메서드를 하거나 사용 하려면 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 
  
##  <a name="deleteallautosavedfiles"></a>  CDataRecoveryHandler::DeleteAllAutosavedFiles  
 현재 자동 저장 된 파일을 모두 삭제 합니다.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현에서는 항상 `TRUE`을 반환합니다.  
  
##  <a name="deleteautosavedfile"></a>  CDataRecoveryHandler::DeleteAutosavedFile  
 지정한 자동 저장 된 파일을 삭제합니다.  
  
```  
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `strAutosavedFile`|자동 저장 된 파일 이름을 포함 하는 문자열입니다.|  
  
### <a name="return-value"></a>반환 값  
 기본 구현은 항상 반환 `TRUE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 자동 저장 된 파일을 삭제할 수 없으면 파일의 이름을 목록에 저장 합니다. 에 대 한 소멸자는 `CDataRecoveryHandler` 해당 목록에 지정 된 각 자동 저장 된 파일을 삭제 하려고 합니다.  
  
##  <a name="generateautosavefilename"></a>  CDataRecoveryHandler::GenerateAutosaveFileName  
 제공된 문서 파일 이름에 연결 된 자동 저장 파일 이름을 생성 합니다.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strDocumentName`  
 문서 이름을 포함 하는 문자열입니다. `GenerateAutosaveFileName` 이 문서 이름을 사용 하 여 해당 자동 저장 파일 이름을 생성 합니다.  
  
### <a name="return-value"></a>반환 값  
 자동 저장 파일 이름에서 생성 된 `strDocumentName`합니다.  
  
### <a name="remarks"></a>설명  
 각 문서 이름에 일대일으로 자동 저장 된 파일 이름이 있습니다.  
  
##  <a name="getautosaveinterval"></a>  CDataRecoveryHandler::GetAutosaveInterval  
 자동 저장 시도 사이의 간격을 반환합니다.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>반환 값  
 자동 저장 사이의 밀리초 수 하려고 시도합니다.  
  
##  <a name="getautosavepath"></a>  CDataRecoveryHandler::GetAutosavePath  
 자동 저장 된 파일의 경로 반환합니다.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 자동 저장 된 문서를 저장할 위치입니다.  
  
##  <a name="getdocumentlistname"></a>  CDataRecoveryHandler::GetDocumentListName  
 문서 이름을 검색 한 `CDocument` 개체입니다.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|에 대 한 포인터는 `CDocument`합니다. `GetDocumentListName` 이 문서의 이름을 검색 `CDocument`합니다.|  
  
### <a name="return-value"></a>반환 값  
 문서 이름 `pDocument`합니다.  
  
### <a name="remarks"></a>설명  
 `CDataRecoveryHandler` 문서 이름에서 키로 사용 하 여 `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, 및 `m_mapDocNameToRestoreBool`합니다. 이러한 매개 변수를 사용 하도록 설정 된 `CDataRecoveryHandler` 모니터링할 `CDocument` 개체, 자동 저장 파일 이름 및 자동 저장 설정 합니다.  
  
##  <a name="getnormaldocumenttitle"></a>  CDataRecoveryHandler::GetNormalDocumentTitle  
 지정된 된 문서에 대 한 일반 제목을 검색합니다.  
  
```  
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|에 대 한 포인터는 `CDocument`합니다.|  
  
### <a name="return-value"></a>반환 값  
 지정된 된 문서에 대 한 일반 제목입니다.  
  
### <a name="remarks"></a>설명  
 문서 일반 제목은 일반적으로 경로 없이 문서의 파일 이름입니다. 제목에 **파일 이름** 필드는 **다른 이름으로 저장** 대화 상자.  
  
##  <a name="getrecovereddocumenttitle"></a>  CDataRecoveryHandler::GetRecoveredDocumentTitle  
 만들고 복구 된 문서에 대 한 title을 반환 합니다.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strDocumentTitle`  
 문서에 대 한 일반 제목입니다.  
  
### <a name="return-value"></a>반환 값  
 복구 문서의 제목입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 복구 된 문서 제목은와 일반 제목 **[복구]** 추가 합니다. 복구 된 제목은 사용자에 게 표시 됩니다 때는 `CDataRecoveryHandler` 자동 저장 된 문서를 복원 하려면 사용자를 쿼리 합니다.  
  
##  <a name="getrestartidentifier"></a>  CDataRecoveryHandler::GetRestartIdentifier  
 응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>반환 값  
 고유 식별자를 다시 시작합니다.  
  
### <a name="remarks"></a>설명  
 다시 시작 식별자는 응용 프로그램의 각 실행에 대해 고유 합니다.  
  
 `CDataRecoveryHandler` 현재 열려 있는 문서에 대 한 레지스트리 정보를 저장 합니다. 다시 시작 식별자는 응용 프로그램을 종료 하 고 다시 시작 하는 다시 시작 관리자를 할 때 제공 된 `CDataRecoveryHandler`합니다. `CDataRecoveryHandler` 다시 시작 식별자를 사용 하 여 이전에 열린 문서의 목록을 검색 합니다. 이 통해는 `CDataRecoveryHandler` 찾기 및 자동 저장 된 파일을 복원 하려고 합니다.  
  
##  <a name="getsavedocumentinfoonidle"></a>  CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 대해 자동 저장을 수행 합니다.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 나타냅니다는 `CDataRecoveryHandler` 현재 유휴 루프가;에 자동으로 저장 `FALSE` 없을 나타냅니다.  
  
##  <a name="getshutdownbyrestartmanager"></a>  CDataRecoveryHandler::GetShutdownByRestartManager  
 다시 시작 관리자 인해 응용 프로그램을 종료 하는지 여부를 나타냅니다.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 다시 시작 관리자를 종료; 응용 프로그램으로 인해 나타냅니다. `FALSE` 않았을 나타냅니다.  
  
##  <a name="initialize"></a>  CDataRecoveryHandler::Initialize  
 `CDataRecoveryHandler` 을(를) 초기화합니다.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 초기화에 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 초기화 프로세스는 레지스트리에서 자동 저장 파일을 저장할 경로 로드 합니다. 경우는 `Initialize` 메서드는이 디렉터리를 찾을 수 없거나 경우 경로 `NULL`, `Initialize` 실패 하 고 반환 `FALSE`합니다.  
  
 사용 하 여 [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) 응용 프로그램 초기화 한 후 자동 저장 경로 변경 하는 `CDataRecoveryHandler`합니다.  
  
 `Initialize` 메서드는 또한 다음 자동 저장을 수행 하는 경우를 모니터링할 타이머를 시작 합니다. 사용 하 여 [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) 응용 프로그램 초기화 한 후 자동 저장 간격을 변경 하려면는 `CDataRecoveryHandler`합니다.  
  
##  <a name="queryrestoreautosaveddocuments"></a>  CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 사용자에 게 대화 상자를 표시 하는 각 문서는 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하는 사용자가 있는지 여부를 결정 합니다.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>설명  
 이 메서드를 표시 하는 응용 프로그램이 유니코드 이면는 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) 사용자에 게 합니다. 그렇지 않은 경우 프레임 워크에서는 [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 사용자 쿼리 합니다.  
  
 후 `QueryRestoreAutosavedDocuments` 모든 응답을 수집, 사용자 로부터 멤버 변수에 정보 저장 `m_mapDocNameToRestoreBool`합니다. 이 메서드는 자동 저장 된 문서를 복원 하지 않습니다.  
  
##  <a name="readopendocumentlist"></a>  CDataRecoveryHandler::ReadOpenDocumentList  
 레지스트리에서 열려 있는 문서 목록을 로드합니다.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 나타냅니다 `ReadOpenDocumentList` 레지스트리;에서 하나 이상의 문서에 대 한 정보를 로드 합니다. `FALSE` 비워진 문서 로드를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 레지스트리에서 열려 있는 문서 정보를 로드 하 고 멤버 변수에 저장 `m_mapDocNameToAutosaveName`합니다.  
  
 후 `ReadOpenDocumentList` 로드 된 모든 데이터를 레지스트리에서 문서 정보를 삭제 합니다.  
  
##  <a name="removedocumentinfo"></a>  CDataRecoveryHandler::RemoveDocumentInfo  
 열린 문서 목록에서 제공된 된 문서를 제거합니다.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|제거 하려면 문서에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 경우 `pDocument` 가; 목록에서 제거 `FALSE` 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 사용자가 문서를 닫을 때 프레임 워크 열린 문서 목록에서 제거 하려면이 메서드를 사용 합니다.  
  
 경우 `RemoveDocumentInfo` 찾을 수 없습니다 `pDocument` 열린 문서 목록에서 그 없으며 반환 `TRUE`합니다.  
  
 이 방법을 사용 하려면 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="reopenpreviousdocuments"></a>  CDataRecoveryHandler::ReopenPreviousDocuments  
 이전에 열려 있는 문서를 엽니다.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 하나 이상의 문서를 열었을; 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 가장 최근의 save 이전에 열린 문서를 엽니다. 문서 저장 되지 않았음을 경우 또는 자동 저장, `ReopenPreviousDocuments` 해당 파일 형식에 대 한 템플릿을 기반으로 하는 빈 문서를 엽니다.  
  
 이 방법을 사용 하려면 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 이 매개 변수 설정 되어 있지 않으면 `ReopenPreviousDocuments` 없으며 반환 `FALSE`합니다.  
  
 이전에 열린 문서의 목록에 저장 된 문서가 없는 경우 `ReopenPreviousDocuments` 없으며 반환 `FALSE`합니다.  
  
##  <a name="restoreautosaveddocuments"></a>  CDataRecoveryHandler::RestoreAutosavedDocuments  
 사용자 입력에 따라 자동 저장 된 문서를 복원 합니다.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드는 문서 성공적으로 복원 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) 사용자 문서를 확인 하려면가 복원 해야 합니다. 자동 저장 된 문서를 복원 하는 사용자가 결정 한 경우 `RestoreAutosavedDocuments` 자동 저장 파일을 삭제 합니다. 그렇지 않으면 `RestoreAutosavedDocuments` 열려 있는 문서 자동 저장 된 버전으로 바꿉니다.  
  
 이 메서드를 하거나 사용 하려면 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 또는 `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="saveopendocumentlist"></a>  CDataRecoveryHandler::SaveOpenDocumentList  
 열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 저장 문서가 열려 있는 경우 또는 성공적으로 저장 된 경우. `FALSE` 문서는 레지스트리에 저장 하는 경우 오류가 발생 했기 때문에 저장 되지 않았습니다.  
  
### <a name="remarks"></a>설명  
 다시 시작 관리자 호출 `SaveOpenDocumentList` 응용 프로그램이 예기치 않게 종료 하는 경우 또는 업그레이드에 대 한 종료 될 때입니다. 사용 하 여 응용 프로그램을 다시 시작 되 면 [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) 열려 있는 문서의 목록을 검색할 수 있습니다.  
  
 이 메서드는 열려 있는 문서의 목록만 저장합니다. 메서드가 [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) 는 문서 자체를 저장 해야 합니다.  
  
##  <a name="setautosaveinterval"></a>  CDataRecoveryHandler::SetAutosaveInterval  
 밀리초 단위로 자동 저장 주기 사이의 시간을 설정 합니다.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nAutosaveInterval`  
 자동 저장 간격 (밀리초) 새 값입니다.  
  
##  <a name="setautosavepath"></a>  CDataRecoveryHandler::SetAutosavePath  
 자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `strAutosavePath`|자동 저장 파일이 저장 된 경로입니다.|  
  
### <a name="remarks"></a>설명  
 자동 저장 디렉터리를 변경 합니다. 움직이지 않으면 현재 자동 저장 된 파일입니다.  
  
##  <a name="setrestartidentifier"></a>  CDataRecoveryHandler::SetRestartIdentifier  
 이 인스턴스에 대 한 고유 다시 시작 식별자를 설정 하는 `CDataRecoveryHandler`합니다.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `strRestartIdentifier`|다시 시작 관리자에 대 한 고유 식별자입니다.|  
  
### <a name="remarks"></a>설명  
 다시 시작 관리자 레지스트리에 열려 있는 문서에 대 한 정보를 기록합니다. 이 정보는 키로 다시 시작 고유 식별자와 함께 저장 됩니다. 다시 시작 식별자는 응용 프로그램의 각 인스턴스에 대해 고유 하므로 응용 프로그램의 여러 인스턴스가 예기치 않게 종료 될 수 있습니다 및 다시 시작 관리자는 각각의 복구할 수 있습니다.  
  
##  <a name="setsavedocumentinfoonidle"></a>  CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 설정 여부는 `CDataRecoveryHandler` 현재 유휴 주기 동안 Windows 레지스트리에 열려 있는 문서 정보를 저장 합니다.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bSaveOnIdle`|`TRUE` 현재 유휴 주기; 동안 문서 정보를 저장 하려면 `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>  CDataRecoveryHandler::SetShutdownByRestartManager  
 다시 시작 관리자에 의해 발생 한 응용 프로그램의 이전 종료 여부를 설정 합니다.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bShutdownByRestartManager`|`TRUE` 다시 시작 관리자는 응용 프로그램을 종료; 했음을 나타내기 위해 `FALSE` 또 다른 이유로 응용 프로그램이 종료 되었음을 나타냅니다.|  
  
### <a name="remarks"></a>설명  
 프레임 워크의 이전 종료 예기치 않은 여부 또는 다시 시작 관리자가 초기화 되었는지 여부에 따라 다르게 동작 합니다.  
  
##  <a name="updatedocumentinfo"></a>  CDataRecoveryHandler::UpdateDocumentInfo  
 사용자를 저장 하기 때문에 문서에 대 한 정보를 업데이트 합니다.  
  
```  
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|저장된 된 문서에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 이 메서드는 자동 저장 된 문서를 삭제 하 고 업데이트 된 문서 정보; `FALSE` 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 사용자가 문서를 저장 하는 경우 더 이상 필요 하기 때문에 응용 프로그램 자동 저장 된 파일을 제거 합니다. `UpdateDocumentInfo` 자동 저장 된 파일을 호출 하 여 삭제 [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)합니다. `UpdateDocumentInfo` 다음 정보를 추가 `pDocument` 목록에 현재 열린 문서 `RemoveDocumentInfo` 삭제 하 고 해당 정보를 하지만 저장 된 문서가 열려 합니다.  
  
 이 방법을 사용 하려면 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)

