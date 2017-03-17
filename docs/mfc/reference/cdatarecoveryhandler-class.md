---
title: "CDataRecoveryHandler 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CDataRecoveryHandler class
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c2a99e32a88b8cb3f12d0961451025596886abb0
ms.lasthandoff: 02/24/2017

---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler 클래스
`CDataRecoveryHandler` 자동으로 저장에 설명 하 고 응용 프로그램이 예기치 않게 종료 되는 경우이 복원 합니다.  
  
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
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|열려 있는 문서의 목록에 문서를 추가합니다.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](#deleteallautosavedfiles)|현재 자동 저장 된 파일을 모두 삭제 합니다.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](#deleteautosavedfile)|지정 된 자동 저장 된 파일을 삭제합니다.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|제공 된 문서 파일 이름에 연결 된 자동 저장 파일 이름을 생성 합니다.|  
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|자동 저장 시도 사이의 간격을 반환합니다.|  
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|자동 저장 된 파일의 경로 반환합니다.|  
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|문서 이름을 검색 한 `CDocument` 개체입니다.|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|지정된 된 문서에 대 한 일반 제목을 검색합니다.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|만들고 복구 된 문서의 제목을 반환 합니다.|  
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 대해 자동 저장을 수행 합니다.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|다시 시작 관리자를 종료 하려면 응용 프로그램으로 인해 있는지 여부를 나타냅니다.|  
|[CDataRecoveryHandler::Initialize](#initialize)|`CDataRecoveryHandler` 을(를) 초기화합니다.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|대화 상자를 사용자에 게 표시 하는 각 문서는 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하는 사용자가 있는지 여부를 결정 합니다.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|레지스트리에서 열려 있는 문서 목록을 로드합니다.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|열려 있는 문서 목록에서 제공된 된 문서를 제거합니다.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|이전에 열려 있는 문서를 엽니다.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|사용자 입력에 따라 자동 저장 된 문서를 복원 합니다.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.|  
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|밀리초 단위로 자동 저장 주기 사이의 시간을 설정 합니다.|  
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.|  
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|이 인스턴스에 대 한 다시 시작 고유 식별자를 설정 하는 `CDataRecoveryHandler`합니다.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|설정 여부는 `CDataRecoveryHandler` 현재 유휴 주기 동안 Windows 레지스트리에 열려 있는 문서 정보를 저장 합니다.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|다시 시작 관리자에 의해 발생 한 응용 프로그램의 이전 종료 여부를 설정 합니다.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|사용자를 저장 하기 때문에 문서에 대 한 정보를 업데이트 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|m_bRestoringPreviousOpenDocs|데이터 복구 처리기 이전에 열려 있는 문서를 닫았다가 다시 열거나 있는지 여부를 나타냅니다.|  
|m_bSaveDocumentInfoOnIdle|다음 유휴 루프에 데이터 복구 처리기 자동으로 저장 문서 있는지 여부를 나타냅니다.|  
|m_bShutdownByRestartManager|다시 시작 관리자를 종료 하려면 응용 프로그램이 있는지 여부를 나타냅니다.|  
|m_dwRestartManagerSupportFlags|응용 프로그램에 대 한 다시 시작 관리자 지원 기능을 나타내는 플래그를 제공 합니다.|  
|m_lstAutosavesToDelete|목록 삭제 되지 않는 원본 문서를 닫은 자동 저장 된 파일입니다. 응용 프로그램이 끝날 때 파일 삭제를 다시 시작 관리자 다시 시도 합니다.|  
|m_mapDocNameToAutosaveName|자동 저장 된 파일 이름에 문서 이름 맵.|  
|m_mapDocNameToDocumentPtr|문서 이름으로 이루어진 지도 [CDocument](../../mfc/reference/cdocument-class.md) 포인터입니다.|  
|m_mapDocNameToRestoreBool|자동 저장 된 문서를 복원 하지 않을 것인지 여부를 나타내는 부울 매개 변수는 문서 이름 맵.|  
|m_mapDocumentPtrToDocName|지도 `CDocument` 문서 이름에 대 한 포인터입니다.|  
|m_mapDocumentPtrToDocTitle|지도 `CDocument` 문서 제목에 대 한 포인터입니다. 이러한 제목 파일을 저장 하는 데 사용 됩니다.|  
|m_nAutosaveInterval|자동으로 저장 하는 간격 (밀리초) 시간입니다.|  
|m_nTimerID|자동 저장 타이머에 대 한 식별자입니다.|  
|m_strAutosavePath|자동 저장 된 문서를 저장할 위치입니다.|  
|m_strRestartIdentifier|다시 시작 관리자에 대 한 GUID의 문자열 표현입니다.|  
  
## <a name="remarks"></a>주의  
 다시 시작 관리자를 사용 하는 `CDataRecoveryHandler` 유지 하는 클래스 열려 있는 모든 문서 및 추적 자동 저장 하 고 필요에 따라 합니다. 자동 저장을 사용 하려면는 [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) 메서드. 지시 하는이 메서드는 `CDataRecoveryHandler` 다음 유휴 루프에서 자동 저장을 수행할 수 있습니다. 다시 시작 관리자 호출 `SetSaveDocumentInfoOnIdle` 때는 `CDataRecoveryHandler` 자동 저장을 수행 해야 합니다.  
  
 모든의 메서드는 `CDataRecoveryHandler` 클래스는 가상 메서드입니다. 사용자 고유의 사용자 지정 데이터 복구 처리기를 만들려면이 클래스의 메서드를 재정의 합니다. 데이터 복구 처리기를 직접 만들거나 관리자를 다시 시작 하지 않는 한 CDataRecoveryHandler 인스턴스화하지 않습니다. [CWinApp 클래스](../../mfc/reference/cwinapp-class.md) 만듭니다는 `CDataRecoveryHandler` 개체는 필요 합니다.  
  
 사용 하기 전에 `CDataRecoveryHandler` 개체를 호출 해야 [CDataRecoveryHandler::Initialize](#initialize)합니다.  
  
 때문에 `CDataRecoveryHandler` 클래스를 다시 시작 관리자 밀접 하 게 연결할 `CDataRecoveryHandler` 전역 매개 변수에 따라 달라 집니다 `m_dwRestartManagerSupportFlags`합니다. 이 매개 변수는 다시 시작 관리자가 권한 및 응용 프로그램과 함께 작용 하는 방법을 결정 합니다. 지정 해야 기존 응용 프로그램에 다시 시작 관리자를 통합 하려면 `m_dwRestartManagerSupportFlags` 주 응용 프로그램의 생성자에 적절 한 값입니다. 다시 시작 관리자를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxdatarecovery.h  
  
##  <a name="autosavealldocumentinfo"></a>CDataRecoveryHandler::AutosaveAllDocumentInfo  
 각 파일에 등록 하는 자동으로 저장 된 `CDataRecoveryHandler` 클래스입니다.  
  
```  
virtual BOOL AutosaveAllDocumentInfo();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하는 경우는 `CDataRecoveryHandler` ; 모든 문서를 저장 합니다. `FALSE` 경우 모든 문서 저장 되지 않았습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 반환 `TRUE` 저장 해야 하는 문서가 없는 경우. 또한 반환 `TRUE` 검색 하는 경우 모든 문서를 저장 하지 않고는 `CWinApp` 또는 `CDocManager` 오류를 생성 하는 응용 프로그램입니다.  
  
 하거나이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 참조 [m_dwRestartManagerSupportFlags](#m_dwrestartmanagersupportflags) 에 대 한 자세한 내용은 합니다.  
  
##  <a name="autosavedocumentinfo"></a>CDataRecoveryHandler::AutosaveDocumentInfo  
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
|[in] `bResetModifiedFlag`|`TRUE`나타내는 `CDataRecoveryHandler` 고려 `pDocument` 을 수정할 수 있습니다. `FALSE` 프레임 워크에서는 간주 나타냅니다 `pDocument` 를 수정 합니다. 이 플래그의 효과 대 한 자세한 내용은 설명 섹션을 참조 합니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE`적절 한 플래그가 설정 된 경우 및 `pDocument` 유효한 `CDocument` 개체입니다.  
  
### <a name="remarks"></a>주의  
 각 `CDocument` 개체에 마지막으로 저장 한 이후 변경 되었는지 여부를 나타내는 플래그입니다. 사용 하 여 [CDocument::IsModified](../../mfc/reference/cdocument-class.md#ismodified) 이 플래그의 상태를 결정 합니다. 경우에 `CDocument` 마지막 저장 이후 변경 되지 않은 `AutosaveDocumentInfo` 해당 문서에 대 한 자동 저장 된 파일을 모두 삭제 합니다. 문서 마지막 저장 이후 변경 된 경우 닫는 사용자 닫기 전에 문서를 저장 하 라는 메시지가 나타납니다.  
  
> [!NOTE]
>  사용 하 여 `bResetModifiedFlag` 수정 되지 않은 문서의 상태를 변경 하려면 저장 되지 않은 데이터가 손실 사용자 표시 될 수 있습니다. 프레임 워크에서 수정 되지 않은 문서를 닫는 묻지 않습니다 사용자에 게 저장할 합니다.  
  
 사용 하 여 예외를 throw 하는이 메서드는 [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c) 매크로 경우 `pDocument` 유효 하지 않거나 `CDocument` 개체입니다.  
  
 하거나이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="cdatarecoveryhandler"></a>CDataRecoveryHandler::CDataRecoveryHandler  
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
|[in] `dwRestartManagerSupportFlags`|다시 시작 관리자의 어떤 옵션이 지원 되는지 나타냅니다.|  
|[in] `nAutosaveInterval`|자동으로 저장 사이의 시간입니다. 이 매개 변수는 밀리초에서입니다.|  
  
### <a name="remarks"></a>주의  
 MFC 프레임 워크는 자동으로 만들고는 `CDataRecoveryHandler` 사용 하는 경우 응용 프로그램에 대 한 개체는 **새 프로젝트** 마법사. 데이터 복구 동작 또는 다시 시작 관리자를 사용자 지정 하려는 경우가 아니면 만들면 안 한 `CDataRecoveryHandler` 개체입니다.  
  
  
##  <a name="createdocumentinfo"></a>CDataRecoveryHandler::CreateDocumentInfo  
 열려 있는 문서의 목록에 문서를 추가합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 메서드를 확인 하는 경우 `pDocument` 문서를 추가 하기 전에 문서 목록에 이미입니다. 경우 `pDocument` 가 이미이 메서드는 목록의 연관 된 자동 저장 된 파일 삭제 `pDocument`합니다.  
  
 하거나이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART` 또는 `AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 
  
##  <a name="deleteallautosavedfiles"></a>CDataRecoveryHandler::DeleteAllAutosavedFiles  
 현재 자동 저장 된 파일을 모두 삭제 합니다.  
  
```  
virtual BOOL DeleteAllAutosavedFiles();
```  
  
### <a name="return-value"></a>반환 값  
 기본 구현에서는 항상 반환 `TRUE`합니다.  
  
##  <a name="deleteautosavedfile"></a>CDataRecoveryHandler::DeleteAutosavedFile  
 지정 된 자동 저장 된 파일을 삭제합니다.  
  
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
  
### <a name="remarks"></a>주의  
 이 메서드는 자동 저장 된 파일을 삭제할 수 없으면 파일의 이름을 목록에 저장 합니다. 에 대 한 소멸자는 `CDataRecoveryHandler` 해당 목록에 지정 된 각 자동 저장 된 파일을 삭제 하려고 합니다.  
  
##  <a name="generateautosavefilename"></a>CDataRecoveryHandler::GenerateAutosaveFileName  
 제공 된 문서 파일 이름에 연결 된 자동 저장 파일 이름을 생성 합니다.  
  
```  
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strDocumentName`  
 문서 이름을 포함 하는 문자열입니다. `GenerateAutosaveFileName`이 문서 이름을 사용 하 여 해당 자동 저장 파일 이름을 생성 합니다.  
  
### <a name="return-value"></a>반환 값  
 자동 저장 파일 이름에서 생성 된 `strDocumentName`합니다.  
  
### <a name="remarks"></a>주의  
 각 문서 이름에 자동 저장 파일 이름의 일대일 매핑이 있습니다.  
  
##  <a name="getautosaveinterval"></a>CDataRecoveryHandler::GetAutosaveInterval  
 자동 저장 시도 사이의 간격을 반환합니다.  
  
```  
virtual int GetAutosaveInterval() const;  
```  
  
### <a name="return-value"></a>반환 값  
 자동 저장 간격 (밀리초)의 수를 가져오려고 시도합니다.  
  
##  <a name="getautosavepath"></a>CDataRecoveryHandler::GetAutosavePath  
 자동 저장 된 파일의 경로 반환합니다.  
  
```  
virtual CString GetAutosavePath() const;  
```  
  
### <a name="return-value"></a>반환 값  
 자동 저장 된 문서를 저장할 위치입니다.  
  
##  <a name="getdocumentlistname"></a>CDataRecoveryHandler::GetDocumentListName  
 문서 이름을 검색 한 `CDocument` 개체입니다.  
  
```  
virtual CString GetDocumentListName(CDocument* pDocument) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|에 대 한 포인터는 `CDocument`합니다. `GetDocumentListName`이 문서 이름을 검색 `CDocument`합니다.|  
  
### <a name="return-value"></a>반환 값  
 문서 이름을 `pDocument`합니다.  
  
### <a name="remarks"></a>주의  
 `CDataRecoveryHandler` 문서 이름을 키로 사용 하 여 `m_mapDocNameToAutosaveName`, `m_mapDocNameToDocumentPtr`, 및 `m_mapDocNameToRestoreBool`합니다. 이러한 매개 변수를 사용 하도록 설정 된 `CDataRecoveryHandler` 모니터링할 `CDocument` 개체, 자동 저장 파일 이름 및 자동 저장 설정 합니다.  
  
##  <a name="getnormaldocumenttitle"></a>CDataRecoveryHandler::GetNormalDocumentTitle  
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
  
### <a name="remarks"></a>주의  
 기본 문서 제목은 일반적으로 경로 없이 문서의 파일 이름입니다. 이 제목에는 **파일 이름** 필드는 **다른 이름으로 저장** 대화 상자.  
  
##  <a name="getrecovereddocumenttitle"></a>CDataRecoveryHandler::GetRecoveredDocumentTitle  
 만들고 복구 된 문서의 제목을 반환 합니다.  
  
```  
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strDocumentTitle`  
 문서에 대 한 일반 제목입니다.  
  
### <a name="return-value"></a>반환 값  
 복구 문서 제목입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로 복구 된 문서 제목은 일반적인 제목을 **[복구]** 추가 되어 있습니다. 사용자에 게 복구 된 제목이 표시 되는지 때는 `CDataRecoveryHandler` 자동 저장 된 문서를 복원 하려면 사용자를 쿼리 합니다.  
  
##  <a name="getrestartidentifier"></a>CDataRecoveryHandler::GetRestartIdentifier  
 응용 프로그램에 대 한 다시 시작 고유 식별자를 검색합니다.  
  
```  
virtual CString GetRestartIdentifier() const;  
```  
  
### <a name="return-value"></a>반환 값  
 고유 식별자를 다시 시작합니다.  
  
### <a name="remarks"></a>주의  
 다시 시작 식별자는 응용 프로그램의 각 실행에 대해 고유 합니다.  
  
 `CDataRecoveryHandler` 정보를 현재 열려 있는 문서에 대 한 레지스트리에 저장 합니다. 다시 시작 식별자를 제공 하면 응용 프로그램을 종료 하 고 다시 시작 하는 다시 시작 관리자를는 `CDataRecoveryHandler`합니다. `CDataRecoveryHandler` 다시 시작 식별자를 사용 하 여 이전에 열려 있는 문서의 목록을 검색할 수 있습니다. 이 통해는 `CDataRecoveryHandler` 찾기 및 자동 저장 된 파일을 복원 하려고 합니다.  
  
##  <a name="getsavedocumentinfoonidle"></a>CDataRecoveryHandler::GetSaveDocumentInfoOnIdle  
 나타냅니다 여부는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 대해 자동 저장을 수행 합니다.  
  
```  
virtual BOOL GetSaveDocumentInfoOnIdle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`나타냅니다는 `CDataRecoveryHandler` 현재 유휴 상태 루프에 자동으로 저장 `FALSE` 없는 나타냅니다.  
  
##  <a name="getshutdownbyrestartmanager"></a>CDataRecoveryHandler::GetShutdownByRestartManager  
 다시 시작 관리자를 종료 하려면 응용 프로그램으로 인해 있는지 여부를 나타냅니다.  
  
```  
virtual BOOL GetShutdownByRestartManager() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`다시 시작 관리자를 종료 합니다; 응용 프로그램으로 인해 나타냅니다. `FALSE` 하지 않았을 나타냅니다.  
  
##  <a name="initialize"></a>CDataRecoveryHandler::Initialize  
 `CDataRecoveryHandler` 을(를) 초기화합니다.  
  
```  
virtual BOOL Initialize();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`초기화에 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 초기화 프로세스에서 레지스트리로부터 자동 저장 파일을 저장 하기 위한 경로 로드 합니다. 하는 경우는 `Initialize` 메서드는이 디렉터리를 찾을 수 없거나 경우 경로 `NULL`, `Initialize` 실패 하 고 반환 `FALSE`합니다.  
  
 사용 하 여 [CDataRecoveryHandler::SetAutosavePath](#setautosavepath) 응용 프로그램 초기화 한 후 자동 저장 경로 변경 하는 `CDataRecoveryHandler`합니다.  
  
 `Initialize` 메서드는 또한 다음 자동 저장을 수행 하는 경우를 모니터링할 타이머를 시작 합니다. 사용 하 여 [CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval) 응용 프로그램 초기화 한 후 자동 저장 간격을 변경 하는 `CDataRecoveryHandler`합니다.  
  
##  <a name="queryrestoreautosaveddocuments"></a>CDataRecoveryHandler::QueryRestoreAutosavedDocuments  
 대화 상자를 사용자에 게 표시 하는 각 문서는 `CDataRecoveryHandler` 자동 저장 합니다. 대화 상자 자동 저장 된 문서를 복원 하는 사용자가 있는지 여부를 결정 합니다.  
  
```  
virtual void QueryRestoreAutosavedDocuments();
```  
  
### <a name="remarks"></a>주의  
 이 메서드를 표시 하는 유니코드 응용 프로그램을 사용 하는 경우는 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) 사용자에 게 있습니다. 그렇지 않으면 프레임 워크 사용 [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 사용자 쿼리 합니다.  
  
 후 `QueryRestoreAutosavedDocuments` 모든 응답을 수집 하는 사용자의 멤버 변수에서 정보를 저장 `m_mapDocNameToRestoreBool`합니다. 이 메서드는 자동 저장 된 문서를 복원 하지 않습니다.  
  
##  <a name="readopendocumentlist"></a>CDataRecoveryHandler::ReadOpenDocumentList  
 레지스트리에서 열려 있는 문서 목록을 로드합니다.  
  
```  
virtual BOOL ReadOpenDocumentList();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`나타내는 `ReadOpenDocumentList` 레지스트리;에서 하나 이상의 문서에 대 한 정보를 로드 합니다. `FALSE` 없는 문서 정보를 로드 하는 것을 나타냅니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 레지스트리에서 열려 있는 문서 정보를 로드 하 고 멤버 변수에 저장 `m_mapDocNameToAutosaveName`합니다.  
  
 후 `ReadOpenDocumentList` 모든 데이터를 로드 레지스트리의 문서 정보를 삭제 합니다.  
  
##  <a name="removedocumentinfo"></a>CDataRecoveryHandler::RemoveDocumentInfo  
 열려 있는 문서 목록에서 제공된 된 문서를 제거합니다.  
  
```  
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pDocument`|제거할 대상 문서에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `pDocument` 목록에서 제거 되었습니다 `FALSE` 오류가 발생 합니다.  
  
### <a name="remarks"></a>주의  
 사용자가 문서를 닫으면 열려 있는 문서의 목록에서 제거 하려면이 메서드를 사용 하는 프레임 워크입니다.  
  
 경우 `RemoveDocumentInfo` 찾을 수 없습니다 `pDocument` 열려 있는 문서의 목록에서 그 없으며 반환 `TRUE`합니다.  
  
 이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="reopenpreviousdocuments"></a>CDataRecoveryHandler::ReopenPreviousDocuments  
 이전에 열려 있는 문서를 엽니다.  
  
```  
virtual BOOL ReopenPreviousDocuments();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`하나 이상의 문서를 열면 됩니다. 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 이전에 열려 있는 문서의 가장 최근 저장을 엽니다. 문서를 저장 하지 경우 또는 자동 저장 된, `ReopenPreviousDocuments` 해당 파일 형식에 대 한 템플릿을 기반으로 새 문서를 엽니다.  
  
 이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다. 이 매개 변수를 설정 하지 않으면 `ReopenPreviousDocuments` 없으며 반환 `FALSE`합니다.  
  
 이전에 열려 있는 문서의 목록에 저장 된 문서가 없는 경우 `ReopenPreviousDocuments` 없으며 반환 `FALSE`합니다.  
  
##  <a name="restoreautosaveddocuments"></a>CDataRecoveryHandler::RestoreAutosavedDocuments  
 사용자 입력에 따라 자동 저장 된 문서를 복원 합니다.  
  
```  
virtual BOOL RestoreAutosavedDocuments();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우이 메서드는 문서를 성공적으로 복원 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) 사용자 문서를 확인 하려면 복원 하 려 합니다. 자동 저장 된 문서를 복원 하는 사용자가 결정 하는 경우 `RestoreAutosavedDocuments` 자동 저장 파일을 삭제 합니다. 그렇지 않으면 `RestoreAutosavedDocuments` 자동 저장 된 버전으로 열려 있는 문서를 바꿉니다.  
  
 하거나이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 또는 `AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
##  <a name="saveopendocumentlist"></a>CDataRecoveryHandler::SaveOpenDocumentList  
 열려 있는 문서의 현재 목록을 Windows 레지스트리에 저장합니다.  
  
```  
virtual BOOL SaveOpenDocumentList();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`저장 엽니다 문서가 없는 경우 또는 성공적으로 저장 된 경우. `FALSE`레지스트리에 저장 하는 문서가 있는 경우 오류가 발생 했기 때문에 저장 되지 않았습니다.  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자 호출 `SaveOpenDocumentList` 응용 프로그램이 예기치 않게 종료 하는 경우 또는 업그레이드에 대 한 종료 되 면 합니다. 사용 하 여 응용 프로그램을 다시 시작 되 면 [CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist) 열려 있는 문서의 목록을 검색할 수 있습니다.  
  
 이 메서드는 열려 있는 문서의 목록만 저장합니다. 메서드가 [CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo) 는 문서 자체를 저장 해야 합니다.  
  
##  <a name="setautosaveinterval"></a>CDataRecoveryHandler::SetAutosaveInterval  
 밀리초 단위로 자동 저장 주기 사이의 시간을 설정 합니다.  
  
```  
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nAutosaveInterval`  
 자동 저장 간격 (밀리초) 새 값입니다.  
  
##  <a name="setautosavepath"></a>CDataRecoveryHandler::SetAutosavePath  
 자동 저장 된 파일을 저장할 디렉터리를 설정 합니다.  
  
```  
virtual void SetAutosavePath(const CString& strAutosavePath);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `strAutosavePath`|자동 저장 파일을 저장할 경로입니다.|  
  
### <a name="remarks"></a>주의  
 자동 저장 디렉터리를 변경 해도 현재 자동 저장 된 파일입니다.  
  
##  <a name="setrestartidentifier"></a>CDataRecoveryHandler::SetRestartIdentifier  
 이 인스턴스에 대 한 다시 시작 고유 식별자를 설정 하는 `CDataRecoveryHandler`합니다.  
  
```  
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `strRestartIdentifier`|다시 시작 관리자에 대 한 고유 식별자입니다.|  
  
### <a name="remarks"></a>주의  
 다시 시작 관리자 레지스트리에 열려 있는 문서에 대 한 정보를 기록합니다. 이 정보는 키로 다시 시작 고유 식별자와 함께 저장 됩니다. 다시 시작 식별자가 응용 프로그램의 각 인스턴스에 대해 고유 하므로 응용 프로그램의 여러 인스턴스가 예기치 않게 종료 될 수 있습니다 및 다시 시작 관리자는 각각의 복구할 수 있습니다.  
  
##  <a name="setsavedocumentinfoonidle"></a>CDataRecoveryHandler::SetSaveDocumentInfoOnIdle  
 설정 여부는 `CDataRecoveryHandler` 현재 유휴 주기 동안 Windows 레지스트리에 열려 있는 문서 정보를 저장 합니다.  
  
```  
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bSaveOnIdle`|`TRUE`현재 유휴 주기; 동안 문서 정보를 저장 하려면 `FALSE to not perform a save`.|  
  
##  <a name="setshutdownbyrestartmanager"></a>CDataRecoveryHandler::SetShutdownByRestartManager  
 다시 시작 관리자에 의해 발생 한 응용 프로그램의 이전 종료 여부를 설정 합니다.  
  
```  
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `bShutdownByRestartManager`|`TRUE`다시 시작 관리자를 종료 합니다; 응용 프로그램으로 인해 되었음을 나타내려면 `FALSE` 응용 프로그램이 다른 이유로 종료 되었음을 나타냅니다.|  
  
### <a name="remarks"></a>주의  
 프레임 워크는 이전 종료 예기치 않은 여부 또는 다시 시작 관리자가 초기화 되었는지 여부에 따라 다르게 동작 합니다.  
  
##  <a name="updatedocumentinfo"></a>CDataRecoveryHandler::UpdateDocumentInfo  
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
 `TRUE`이 메서드는 자동 저장 된 문서를 삭제 하 고 업데이트 된 문서 정보; `FALSE` 오류가 발생 합니다.  
  
### <a name="remarks"></a>주의  
 사용자가 문서를 저장 하는 경우 응용 프로그램이 더 이상 필요 하기 때문에 자동 저장 된 파일을 제거 합니다. `UpdateDocumentInfo`호출 하 여 자동 저장 된 파일을 삭제 [CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)합니다. `UpdateDocumentInfo`다음 정보를 추가 `pDocument` 목록에 현재 열에 설명 하기 때문에 `RemoveDocumentInfo` 이러한 정보를 하지만 저장 된 삭제 문서가 열려 있습니다.  
  
 이 메서드를 사용 하 여 `AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES` 에 설정 되어 있어야 `m_dwRestartManagerSupportFlags`합니다.   
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [방법: 다시 시작 관리자 지원 추가](../../mfc/how-to-add-restart-manager-support.md)


