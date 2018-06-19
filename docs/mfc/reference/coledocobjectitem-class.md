---
title: COleDocObjectItem 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDocObjectItem
- AFXOLE/COleDocObjectItem
- AFXOLE/COleDocObjectItem::COleDocObjectItem
- AFXOLE/COleDocObjectItem::DoDefaultPrinting
- AFXOLE/COleDocObjectItem::ExecCommand
- AFXOLE/COleDocObjectItem::GetActiveView
- AFXOLE/COleDocObjectItem::GetPageCount
- AFXOLE/COleDocObjectItem::OnPreparePrinting
- AFXOLE/COleDocObjectItem::OnPrint
- AFXOLE/COleDocObjectItem::QueryCommand
- AFXOLE/COleDocObjectItem::Release
dev_langs:
- C++
helpviewer_keywords:
- COleDocObjectItem [MFC], COleDocObjectItem
- COleDocObjectItem [MFC], DoDefaultPrinting
- COleDocObjectItem [MFC], ExecCommand
- COleDocObjectItem [MFC], GetActiveView
- COleDocObjectItem [MFC], GetPageCount
- COleDocObjectItem [MFC], OnPreparePrinting
- COleDocObjectItem [MFC], OnPrint
- COleDocObjectItem [MFC], QueryCommand
- COleDocObjectItem [MFC], Release
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af2b13b8da5f70cf55b47ddf3b7864f9f9151a40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373581"
---
# <a name="coledocobjectitem-class"></a>COleDocObjectItem 클래스
액티브 문서 포함을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](#coledocobjectitem)|생성 된 `COleDocObject` 항목입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](#dodefaultprinting)|기본 프린터 설정은 사용 하 여 컨테이너 응용 프로그램의 문서를 인쇄 합니다.|  
|[COleDocObjectItem::ExecCommand](#execcommand)|사용자가 지정한 명령을 실행 합니다.|  
|[COleDocObjectItem::GetActiveView](#getactiveview)|문서의 현재 보기를 검색합니다.|  
|[COleDocObjectItem::GetPageCount](#getpagecount)|컨테이너 응용 프로그램의 문서에는 페이지 수를 검색합니다.|  
|[COleDocObjectItem::OnPreparePrinting](#onprepareprinting)|컨테이너 응용 프로그램의 문서 인쇄를 위해 준비합니다.|  
|[COleDocObjectItem::OnPrint](#onprint)|컨테이너 응용 프로그램의 문서를 인쇄 합니다.|  
|[COleDocObjectItem::QueryCommand](#querycommand)|사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.|  
|[COleDocObjectItem::Release](#release)|OLE 링크 된 항목에 대 한 연결을 해제 하 고 열려 있으면 닫습니다. 클라이언트 항목을 제거 하지 않습니다.|  
  
## <a name="remarks"></a>설명  
 MFC, 액티브 문서는 포함 하는 방식는 정기적이 고 내부 편집 가능한, 다음과 같은 차이와 비슷하게 처리 됩니다.  
  
-   `COleDocument`-파생된 클래스에는 여전히 현재 포함 된 항목의 목록을 유지 관리 합니다; 그러나 이러한 항목을 수 있습니다 `COleDocObjectItem`-파생 항목입니다.  
  
-   액티브 문서는 활성 상태 이면에 내부 활성화 되었을 때 보기의 전체 클라이언트 영역을 차지 합니다.  
  
-   액티브 문서 컨테이너에 대해 모든 권한을 갖고는 **도움말** 메뉴.  
  
-   **도움말** 메뉴 액티브 문서 컨테이너와 서버 모두에 대 한 메뉴 항목을 포함 합니다.  
  
 액티브 문서 컨테이너 소유 하 고는 **도움말** 메뉴 컨테이너에 대 한 책임이 전달 서버 **도움말** 메뉴 메시지를 서버에 있습니다. 이러한 통합에 의해 처리 됩니다 `COleDocObjectItem`합니다.  
  
 개요를 보려면 메뉴 병합 및 현재 문서 활성화에 대 한 자세한 내용은 [액티브 문서 포함](../../mfc/active-document-containment.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [활성화](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="coledocobjectitem"></a>  COleDocObjectItem::COleDocObjectItem  
 초기화 하려면이 함수 호출의 `COleDocObjectItem` 개체입니다.  
  
```  
COleDocObjectItem(COleDocument* pContainerDoc = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pContainerDoc`  
 에 대 한 포인터는 `COleDocument` 액티브 문서 컨테이너 역할 개체입니다. 이 매개 변수 해야 **NULL** 사용할 수 있도록 **만들 수 있습니다**합니다. 비-를 사용 하 여 OLE 항목은 생성 하는 일반적으로 **NULL** 문서 포인터입니다.  
  
##  <a name="dodefaultprinting"></a>  COleDocObjectItem::DoDefaultPrinting  
 기본 설정을 사용 하 여 문서에는 프레임 워크에서 호출 됩니다.  
  
```  
static HRESULT DoDefaultPrinting(
    CView* pCaller,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCaller`  
 에 대 한 포인터는 [CView](../../mfc/reference/cview-class.md) 인쇄 명령을 전송 하는 개체입니다.  
  
 `pInfo`  
 에 대 한 포인터는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 인쇄 작업을 설명 하는 개체입니다.  
  
##  <a name="execcommand"></a>  COleDocObjectItem::ExecCommand  
 사용자가 지정한 명령을 실행 하려면이 함수를 호출 합니다.  
  
```  
HRESULT ExecCommand(
    DWORD nCmdID,  
    DWORD nCmdExecOpt = OLECMDEXECOPT_DONTPROMPTUSER,  
    const GUID* pguidCmdGroup = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCmdID`  
 실행할 명령의 식별자입니다. 로 식별 되는 그룹에 있어야 `pguidCmdGroup`합니다.  
  
 `nCmdExecOpt`  
 명령 실행 옵션을 지정합니다. 사용자에 게 확인 하지 않고 명령을 실행 하는 기본적으로 설정 합니다. 참조 [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) 값 목록에 대 한 합니다.  
  
 `pguidCmdGroup`  
 명령 그룹의 고유 식별자입니다. 기본적으로 **NULL**, 표준 그룹을 지정 하는 합니다. 전달 된 명령을 `nCmdID` 그룹에 속해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공; 그렇지 않으면 반환 다음 오류 코드 중 하나입니다.  
  
|값|설명|  
|-----------|-----------------|  
|**E_UNEXPECTED**|예기치 않은 오류가 발생 했습니다.|  
|**E_FAIL**|오류가 발생 했습니다.|  
|**E_NOTIMPL**|MFC 나타냅니다 자체를 변환 하 고 명령 디스패치 시도해 야 합니다.|  
|**OLECMDERR_E_UNKNOWNGROUP**|`pguidCmdGroup` 이 아닌 **NULL** 하지만 인식 된 명령 그룹을 지정 하지 않습니다.|  
|**OLECMDERR_E_NOTSUPPORTED**|`nCmdID` 그룹 pGroup에서 유효한 명령으로 인식 되지 않습니다.|  
|**OLECMDERR_DISABLED**|로 식별 되는 명령을 `nCmdID` 비활성화 되 고 실행할 수 없습니다.|  
|**OLECMDERR_NOHELP**|호출자로 식별 되는 명령에 도움을 요청 `nCmdID` 있지만 도움말이 없습니다.|  
|**OLECMDERR_CANCELLED**|사용자는 실행을 취소 합니다.|  
  
### <a name="remarks"></a>설명  
 `pguidCmdGroup` 및 `nCmdID` 매개 변수를 함께 호출할 명령을 고유 하 게 식별 합니다. `nCmdExecOpt` 매개 변수는 정확한 수행할 동작을 지정 합니다.  
  
##  <a name="getactiveview"></a>  COleDocObjectItem::GetActiveView  
 이 멤버 함수에 포인터를 얻으려면 호출는 `IOleDocumentView` 현재 활성 뷰의 인터페이스입니다.  
  
```  
LPOLEDOCUMENTVIEW GetActiveView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [IOleDocumentView](http://msdn.microsoft.com/library/windows/desktop/ms678455) 현재 활성 뷰의 인터페이스입니다. 현재 뷰가 없으면 반환 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 반환 된 참조 횟수 `IOleDocumentView` 포인터는이 함수에서 반환 되기 전에 증가 하지 않습니다.  
  
##  <a name="getpagecount"></a>  COleDocObjectItem::GetPageCount  
 문서에서 페이지의 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetPageCount(
    LPLONG pnFirstPage,  
    LPLONG pcPages);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnFirstPage*  
 문서에서 첫 번째 페이지의 수에 대 한 포인터입니다. 수 **NULL**,이 숫자 필요 하지 않은 호출자에 게 나타냅니다.  
  
 *pcPages*  
 문서에서 페이지의 총 수에 대 한 포인터입니다. 수 **NULL**,이 숫자 필요 하지 않은 호출자에 게 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="onprepareprinting"></a>  COleDocObjectItem::OnPreparePrinting  
 이 멤버 함수는 문서 인쇄를 위해 준비 하는 프레임 워크에서 호출 됩니다.  
  
```  
static BOOL OnPreparePrinting(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCaller`  
 에 대 한 포인터는 [CView](../../mfc/reference/cview-class.md) 인쇄 명령을 전송 하는 개체입니다.  
  
 `pInfo`  
 에 대 한 포인터는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 인쇄 작업을 설명 하는 개체입니다.  
  
 `bPrintAll`  
 전체 문서 인쇄할 수 있는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="onprint"></a>  COleDocObjectItem::OnPrint  
 이 멤버 함수는 문서를 인쇄 하기 위해 프레임 워크에 의해 호출 됩니다.  
  
```  
static void OnPrint(
    CView* pCaller,  
    CPrintInfo* pInfo,  
    BOOL bPrintAll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCaller`  
 인쇄 명령을 보내는 CView 개체에 대 한 포인터입니다.  
  
 `pInfo`  
 에 대 한 포인터는 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md) 인쇄 작업을 설명 하는 개체입니다.  
  
 `bPrintAll`  
 전체 문서 인쇄할 수 있는지 여부를 지정 합니다.  
  
##  <a name="querycommand"></a>  COleDocObjectItem::QueryCommand  
 사용자 인터페이스 이벤트에 의해 생성되는 하나 이상 명령의 상태를 쿼리합니다.  
  
```  
HRESULT QueryCommand(
    ULONG nCmdID,  
    DWORD* pdwStatus,  
    OLECMDTEXT* pCmdText =NULL,  
    const GUID* pguidCmdGroup =NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCmdID`  
 식별자에 대 한 쿼리 중인 명령입니다.  
  
 `pdwStatus`  
 이 쿼리의 결과로 반환 하는 플래그에 대 한 포인터입니다. 가능한 값 목록은 참조 [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237)합니다.  
  
 `pCmdText`  
 에 대 한 포인터는 [OLECMDTEXT](http://msdn.microsoft.com/library/windows/desktop/ms693314) 단일 명령에 대 한 이름 및 상태 정보를 반환 하는 구조입니다. 수 **NULL** 를 나타내는 호출자에 게가이 정보가 필요 하지 않습니다.  
  
 `pguidCmdGroup`  
 명령 그룹의 고유 식별자 수 **NULL** 표준 그룹을 지정할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값의 전체 목록을 보려면 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) Windows sdk에서입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [IOleCommandTarget::QueryStatus](http://msdn.microsoft.com/library/windows/desktop/ms688491) 메서드를 Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="release"></a>  COleDocObjectItem::Release  
 OLE 링크 된 항목에 대 한 연결을 해제 하 고 열려 있으면 닫습니다. 클라이언트 항목을 제거 하지 않습니다.  
  
```  
virtual void Release(OLECLOSE dwCloseOption = OLECLOSE_NOSAVE);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCloseOption`  
 OLE 항목 로드 된 상태로 돌아오면 어떤 상황에서 저장을 지정 하는 플래그입니다. 가능한 값 목록은 참조 [COleClientItem::Close](../../mfc/reference/coleclientitem-class.md#close)합니다.  
  
### <a name="remarks"></a>설명  
 클라이언트 항목을 제거 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MFCBIND](../../visual-cpp-samples.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleClientItem 클래스](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem 클래스](../../mfc/reference/cdocobjectserveritem-class.md)
