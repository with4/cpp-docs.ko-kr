---
title: 'TN041: MFC OLE 2로 MFC OLE1 마이그레이션 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE1 [MFC]
- migrating OLE1 to OLE2
- migration [MFC], OLE1 to OLE2
- OLE2 [MFC]
- porting OLE1 to OLE2
- converting OLE1 to OLE2
- upgrading Visual C++ applications [MFC], OLE1 to OLE2
- TN041
ms.assetid: 67f55552-4b04-4ddf-af0b-4d9eaf5da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78faa19263ff0ea03aac891c9be3a6114f7f9a48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tn041-mfcole1-migration-to-mfcole-2"></a>TN041: MFC/OLE 2로 MFC/OLE1 마이그레이션
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
## <a name="general-issues-relating-to-migration"></a>마이그레이션에 관련 된 일반적인 문제  
 (이상) MFC 2.5에서 OLE 2 클래스에 대 한 디자인 목표 중 하나 대부분의 OLE 1.0 지원에 대 한 MFC 2.0에서 제 자리에 배치 하는 동일한 아키텍처를 유지 하는 것 이었습니다. 결과적으로, 여러 MFC 2.0에서 동일한 OLE 클래스에에서 여전히 존재이 버전의 MFC (`COleDocument`, `COleServerDoc`, `COleClientItem`, `COleServerItem`). 또한 이러한 클래스의 Api의 대부분은 동일 합니다. 그러나 OLE 2 이므로 OLE 1.0 많이 달라 있는 일부 세부 정보가 변경 될 수 있습니다. MFC 2.0 OLE1 지원 잘 알고 있다면, MFC의 2.0 지원을 통해 집에서 느낄 수 있습니다.  
  
 기존 MFC/OLE1 응용 프로그램을 수행 하 고 OLE 2 기능을 추가, 경우 먼저이 참고를 참고 하십시오. 이 노트에서는 MFC/OLE 2에 OLE1 기능을 이식 하는 동안 발생할 수 하 고 다음 MFC 2.0에 포함 된 두 개의 응용 프로그램을 이식 하는 동안 발견 되지 않은 문제를 설명 몇 가지 일반적인 문제: MFC OLE 샘플 [OCLIENT](../visual-cpp-samples.md) 및 [HIERSVR](../visual-cpp-samples.md)합니다.  
  
## <a name="mfc-documentview-architecture-is-important"></a>MFC 문서/뷰 아키텍처는 중요 한  
 응용 프로그램에서는 MFC의 문서/뷰 아키텍처를 사용 하지 OLE 2 지원 응용 프로그램에 추가 하려는 경우 이제는 문서/뷰를 이동 합니다. 응용 프로그램의 기본 제공 아키텍처 및 MFC 구성 요소에 사용 되 면 여러 가지 MFC의 OLE 2 클래스의 이점을 실현만 됩니다.  
  
 MFC 아키텍처를 사용 하지 않고 서버 또는 컨테이너를 구현 하는 있지만 권장 하지는 않습니다.  
  
## <a name="use-mfc-implementation-instead-of-your-own"></a>사용자 고유의 대신 사용 하 여 MFC 구현  
 와 같은 클래스 구현 "MFC"고정 `CToolBar`, `CStatusBar`, 및 `CScrollView` OLE 2 지원에 대 한 특수 사례 코드를 기본 제공 합니다. 따라서 응용 프로그램에서 이러한 클래스를 사용할 수 있는 경우에 넣을 수 있도록 OLE 인식 과정에서 작업할 수 있습니다. 이러한 목적을 위해 클래스 "롤 your own" 여기에 가능한 동작은 하지만 것이 좋습니다. 유사한 기능을 구현 해야 하는 경우 MFC 소스 코드 있으면 OLE 미세한 사항 중 일부는 처리에 대 한 뛰어난 참조 (특히 내부 활성화에 관한).  
  
## <a name="examine-the-mfc-sample-code"></a>MFC 샘플 코드 확인  
 MFC 샘플 OLE 기능을 포함 하는 여러 가지가 있습니다. 각 응용이 프로그램은 다른 각도에서 OLE를 구현합니다.  
  
- [HIERSVR](../visual-cpp-samples.md) 서버 응용 프로그램으로 사용 하기 위해 주로 사용 합니다. MFC/OLE1 응용 프로그램으로 MFC 2.0에 포함 된 및 된 MFC/OLE 2로 이식 있으며 OLE 2에서 사용할 수 있는 많은 OLE 기능이 구현 되도록 확장 됩니다.  
  
- [OCLIENT](../visual-cpp-samples.md) 독립 실행형 컨테이너 응용 프로그램, 컨테이너 관점에서 대부분의 OLE 기능을 보여 주기 위한 것입니다. 너무 것 MFC 2.0에서 포팅된 및 다양 한 사용자 지정 클립보드 형식 및 포함 된 항목에 대 한 링크와 같은 고급 OLE 기능을 지원 하도록 확장 됩니다.  
  
- [DRAWCLI](../visual-cpp-samples.md) 이 응용 프로그램 OLE 컨테이너 지원을 구현 훨씬 같이 OCLIENT를 제외 하 고 기존 개체 지향 드로잉 프로그램의 프레임 워크 내에서 작업을 수행 합니다. OLE 컨테이너 지원을 구현 하 고 기존 응용 프로그램에 통합할 수 있는 방법을 있습니다 보여 합니다.  
  
- [SUPERPAD](../visual-cpp-samples.md) 세밀 하 게에서는 독립 실행형 응용 프로그램 뿐만 아니라이 응용 프로그램 OLE 서버 이기도 합니다. 구현 서버 지원은 아직 시간이 최소화 된 합니다. 특히 중요 데이터를 클립보드에 복사할 OLE 클립보드 서비스를 사용 하는 방법 하지만 사용 하 여 Windows "edit" 컨트롤에 기본 제공 기능이 클립보드 붙여넣기 기능을 구현 합니다. 기존의 Windows API 사용 뿐만 아니라 새로운 OLE Api와의 통합 흥미로운 혼합 하 여 보여 줍니다.  
  
 샘플 응용 프로그램에 대 한 자세한 내용은 MFC 샘플 "도움말"을 참조 하십시오.  
  
## <a name="case-study-oclient-from-mfc-20"></a>사례 연구: OCLIENT MFC 2.0에서  
 위에서 설명 했 듯이 [OCLIENT](../visual-cpp-samples.md) 고 MFC 2.0에 포함 된 OLE MFC/OLE1를 구현 합니다. 기준인이 응용 프로그램 처음 변환 MFC/OLE 2 클래스를 사용 하는 단계에 대 한 설명은 다음과 같습니다. 초기 포트 MFC/OLE 클래스 이해를 돕기 위해 완료 된 후에 다양 한 기능이 추가 되었습니다. 이러한 기능은 다루지 않습니다. 이러한 고급 기능에 대 한 자세한 내용은 샘플 자체를 참조 하십시오.  
  
> [!NOTE]
>  컴파일러 오류 및 단계별 프로세스는 Visual c + + 2.0으로 만들어졌습니다. Visual c + + 4.0 특정 오류 메시지 및 위치 변경 수 있습니다 하지만 개념 정보 유효한 상태를 유지 합니다.  
  
## <a name="getting-it-up-and-running"></a>해당 시작 및 실행  
 MFC/OLE로 OCLIENT 샘플 포트를 사용 하는 접근 방식은 빌드하고 발생 시키는 확실 한 컴파일러 오류를 수정 하 여 먼저입니다. MFC 2.0에서 OCLIENT 샘플을 사용 하 고이 버전의 MFC에서 컴파일할 경우에 많은 오류를 해결 하려면 되지 않았는지를 찾을 수 있습니다. 발생 한 순서 대로 오류에 대 한 설명은 다음과 같습니다.  
  
## <a name="compile-and-fix-errors"></a>컴파일 및 오류 수정  
  
```  
\oclient\mainview.cpp(104) : error C2660: 'Draw' : function does not take 4 parameters  
```  
  
 첫 번째 오류 걱정거리 `COleClientItem::Draw`합니다. MFC/OLE1 MFC/OLE 버전에서는 보다 더 많은 매개 변수가 걸렸습니다. 추가 매개 변수 필요한 및 (이 예에서는)에서 같이 일반적으로 NULL 했습니다 없는 경우가 많습니다. 이 버전의 MFC 그리고 CDC 메타 파일 DC 때는 lpWBounds에 대 한 값을 자동으로 결정할 수입니다. 또한 pFormatDC 매개 변수는 더 이상 필요한 프레임 워크 "DC"의 특성에 전달 된 pDC에서 빌드됩니다. 이 문제를 해결 하려면 단순히 두가 제거 되므로 추가 그리기 호출에 매개 변수는 NULL입니다.  
  
```  
\oclient\mainview.cpp(273) : error C2065: 'OLE_MAXNAMESIZE' : undeclared identifier  
\oclient\mainview.cpp(273) : error C2057: expected constant expression  
\oclient\mainview.cpp(280) : error C2664: 'CreateLinkFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(286) : error C2664: 'CreateFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
\oclient\mainview.cpp(288) : error C2664: 'CreateStaticFromClipboard' : cannot convert parameter 1 from 'char [1]' to 'enum ::tagOLERENDER '  
```  
  
 결과 사실에서 위의 오류 하의 모든는 **COleClientItem::CreateXXXX** MFC/OLE1의 함수는 항목을 나타내는 고유한 이름을 전달 한다고 필요 합니다. 이 기본 OLE API의 요구 사항 이었습니다. 이 OLE 2 DDE (이름이 DDE 대화에 사용 된)의 기본 통신 메커니즘으로 사용 하지 않는 때문 MFC/OLE 2에 필요 하지 않습니다. 이 문제를 해결 하려면 제거할 수 있습니다는 **CreateNewName** 에 대 한 모든 참조도 작동 합니다. 무엇 각 MFC/OLE 함수 예상이 버전에 대 한 호출에 커서를 놓고 F1 키를 누르면 하기만 확인 하는 것이 쉽습니다.  
  
 와 비슷한 다른 영역에는 OLE 2 클립보드 처리할입니다. OLE1, 클립보드와 Windows 클립보드 Api 상호 작용 사용 있습니다. OLE 2를 다른 메커니즘으로 수행 됩니다. MFC/OLE1 Api 클립보드를 복사 하기 전에 열려 있었던 것으로 간주 한 `COleClientItem` 클립보드로 개체입니다. 이 더 이상 필요 하며 모든 MFC/OLE 클립보드 작업이 실패 하면 합니다. 종속성을 제거 하는 코드를 편집 하는 동안 **CreateNewName**을 열고 닫는 Windows 클립보드 코드도 제거 해야 합니다.  
  
```  
\oclient\mainview.cpp(332) : error C2065: 'AfxOleInsertDialog' : undeclared identifier  
\oclient\mainview.cpp(332) : error C2064: term does not evaluate to a function  
\oclient\mainview.cpp(344) : error C2057: expected constant expression  
\oclient\mainview.cpp(347) : error C2039: 'CreateNewObject' : is not a member of 'CRectItem'  
```  
  
 이러한 오류가 발생할는 **CMainView::OnInsertObject** 처리기입니다. "새 개체 삽입" 명령을 처리 하는 또 다른 영역은 몇 가지가 다소 변경 되었습니다. 이 경우 단순히 새 OLE 컨테이너 응용 프로그램에 대 한 응용 프로그램 마법사에서 제공 되는 원본 구현을 병합 하는 가장 쉬운 방법입니다. 사실, 이것이 다른 응용 프로그램 이식에 적용할 수 있는 방법입니다. MFC/OLE1 호출 하 여 "개체 삽입" 대화 상자 표시 **AfxOleInsertDialog** 함수입니다. 이 버전에서 작성 한 **COleInsertObject** 대화 상자 개체와 호출 `DoModal`합니다. 와 새로운 OLE 항목이 생성 됩니다는 또한는 **CLSID** classname 문자열 대신 합니다. 최종 결과 다음과 같이 표시 됩니다.  
  
```  
COleInsertDialog dlg;  
if (dlg.DoModal() != IDOK)  
    return; 
 
BeginWaitCursor();

 
CRectItem* pItem = NULL;  
TRY  
{ *// First create the C++ object  
    pItem = GetDocument()->CreateItem();
ASSERT_VALID(pItem);

 *// Initialize the item from the dialog data.  
    if (!dlg.CreateItem(pItem))  
    AfxThrowMemoryException();
*// any exception will do  
    ASSERT_VALID(pItem);

 *// run the object if appropriate  
    if (dlg.GetSelectionType() == 
    COleInsertDialog::createNewItem) 
    pItem->DoVerb(OLEIVERB_SHOW,
    this);

 *// update right away  
    pItem->UpdateLink();
pItem->UpdateItemRectFromServer();

 *// set selection to newly inserted item  
    SetSelection(pItem);

 pItem->Invalidate();

}  
CATCH (CException,
    e)  
{ *// clean up item  
    if (pItem != NULL)  
    GetDocument()->DeleteItem(pItem);

 
    AfxMessageBox(IDP_FAILED_TO_CREATE);

} 
END_CATCH  
 
EndWaitCursor();
```  
  
> [!NOTE]
>  새 개체 삽입 다를 수 있습니다 응용 프로그램에 대 한):  
  
 포함 하는 데 필요한 이기도 \<afxodlgs.h >에 대 한 선언을 포함 하는 **COleInsertObject** 으로 대화 상자 클래스는 다른 표준 대화 상자에서 MFC 제공 합니다.  
  
```  
\oclient\mainview.cpp(367) : error C2065: 'OLEVERB_PRIMARY' : undeclared identifier  
\oclient\mainview.cpp(367) : error C2660: 'DoVerb' : function does not take 1 parameters  
```  
  
 이러한 오류는 않기 때문에 일부 OLE1 상수 OLE 2에서 변경 된 개념에서 발생 하는 동일 합니다. 이 경우 **OLEVERB_PRIMARY** 로 변경 되었습니다 `OLEIVERB_PRIMARY`합니다. 기본 동사 OLE1 및 OLE 2에서는 일반적으로 사용자가 항목에는 컨테이너에 의해 실행 됩니다.  
  
 또한 `DoVerb` 추가 매개 변수가 더 길어진-보기에 대 한 포인터 (`CView`*). 이 매개 변수는 "비주얼 편집" (또는 내부 활성화) 구현에 사용 됩니다. 이제이 이번에이 기능을 구현 하지 않는 때문에 NULL로 매개 변수를 설정 합니다.  
  
 재정의 해야 하는 프레임 워크 활성화 되지 않습니다 전체에 시도를 `COleClientItem::CanActivate` 다음과 같습니다.  
  
```  
BOOL CRectItem::CanActivate()  
{  
    return FALSE;  
}  
 
\oclient\rectitem.cpp(53) : error C2065: 'GetBounds' : undeclared identifier  
\oclient\rectitem.cpp(53) : error C2064: term does not evaluate to a function  
\oclient\rectitem.cpp(84) : error C2065: 'SetBounds' : undeclared identifier  
\oclient\rectitem.cpp(84) : error C2064: term does not evaluate to a function  
```  
  
 MFC/OLE1에서 **COleClientItem::GetBounds** 및 **SetBounds** 쿼리하고 항목의 범위를 조작 하는 데 사용 된 (의 **왼쪽** 및 **top**설정 된 멤버 0). MFC/OLE 2에서가 더 직접적 지원할 `COleClientItem::GetExtent` 및 `SetExtent`를 처리 하는 **크기** 또는 `CSize` 대신 합니다.  
  
 새 SetItemRectToServer 프로그램에 대 한 코드와 UpdateItemRectFromServer 호출은 다음과 유사 합니다.  
  
```  
BOOL CRectItem::UpdateItemRectFromServer()  
{  
    ASSERT(m_bTrackServerSize);

 CSize size;  
    if (!GetExtent(&size))  
    return FALSE;    // blank  
 *// map from HIMETRIC to screen coordinates  
 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.LPtoDP(&size);

 } *// just set the item size  
    if (m_rect.Size() != size)  
 { *// invalidate the old size/position  
    Invalidate();
m_rect.right = m_rect.left + size.cx;  
    m_rect.bottom = m_rect.top + size.cy; *// as well as the new size/position  
    Invalidate();

 }  
    return TRUE;  
}  
 
BOOL CRectItem::SetItemRectToServer()  
{ *// set the official bounds for the embedded item  
    CSize size = m_rect.Size();

 {  
    CClientDC screenDC(NULL);

    screenDC.SetMapMode(MM_HIMETRIC);

 screenDC.DPtoLP(&size);

 }  
    TRY 
 {  
    SetExtent(size);
*// may do a wait  
 }  
    CATCH(CException, e)  
 {  
    return FALSE;  // links will not allow SetBounds  
 }  
    END_CATCH 
    return TRUE;  
}  
 
\oclient\frame.cpp(50) : error C2039: 'InWaitForRelease' : is not a member of 'COleClientItem'  
\oclient\frame.cpp(50) : error C2065: 'InWaitForRelease' : undeclared identifier  
\oclient\frame.cpp(50) : error C2064: term does not evaluate to a function  
```  
  
 MFC/OLE1 동기 API에는 서버에 대 한 컨테이너에서 호출 된 *시뮬레이션*OLE1 대부분의 경우에서 기본적으로 비동기 때문에, 합니다. 진행 중인 비동기 호출이 해결 되지 않은 사용자 로부터 명령을 처리 하기 전에 확인 해야 했습니다. MFC/OLE1 제공 되는 **COleClientItem::InWaitForRelease** 이렇게 하는 것에 대 한 함수입니다. MFC/OLE 2에서이 아니므로 필요한 OnCommand 재정의 CMainFrame 모두 함께 제거를 할 수 있습니다.  
  
 이 시점에서 OCLIENT 컴파일하고 연결 합니다.  
  
## <a name="other-necessary-changes"></a>필요한 다른 변경  
 그러나 수행 되지 않는 실행에서 OCLIENT 유지 합니다는 몇 가지 있습니다. 않고 나중에 이러한 문제를 해결 하는 것이 좋습니다.  
  
 첫째, OLE 라이브러리를 초기화 하는 데 필요한 되었습니다. 호출 하 여 이렇게 **AfxOleInit** 에서 `InitInstance`:  
  
```  
if (!AfxOleInit())  
{  
    AfxMessageBox("Failed to initialize OLE libraries");

    return FALSE;  
}  
```  
  
 또한 매개 변수 목록 변경 내용에 대 한 가상 함수에 대해 확인 하는 것이 좋습니다. 이러한 함수는 하나는 `COleClientItem::OnChange`, 모든 MFC/OLE 컨테이너 응용 프로그램에 재정의 합니다. 온라인 도움말을 보고는 추가 'DWORD dwParam' 추가 되는지 볼 수 있습니다. 새 CRectItem::OnChange 모양은 다음과 같습니다.  
  
```  
void   
CRectItem::OnChange(OLE_NOTIFICATION wNotification, DWORD dwParam)  
{  
    if (m_bTrackServerSize&& 
 !UpdateItemRectFromServer())  
 { *// Blank object  
    if (wNotification == OLE_CLOSED)  
 { *// no data received for the object - destroy it  
    ASSERT(!IsVisible());

 GetDocument()->DeleteItem(this);

    return; // no update (item is gone now)  
 }  
 }  
    if (wNotification != OLE_CLOSED)  
    Dirty();
Invalidate();
*// any change will cause a redraw  
}  
```  
  
 MFC/OLE1 컨테이너 응용 프로그램에서 문서 클래스 파생 **COleClientDoc**합니다. MFC/OLE 2에서이 클래스는 제거 되 고 바뀝니다 `COleDocument` (이 새 조직을 쉽게 컨테이너/서버 응용 프로그램을 빌드할). 한 `#define` 매핑하는 **COleClientDoc** 를 `COleDocument` OCLIENT 같은 MFC/OLE 2로 MFC/OLE1 응용 프로그램 이식 간소화 하기 위해. 기능 중 하나에서 제공 하지 `COleDocument` 에서 제공한 **COleClientDoc** 표준 명령 메시지 맵 항목입니다. 이 작업을 수행 하므로 또한 사용 하 여 해당 서버 응용 프로그램 `COleDocument` (간접적으로)을 포함 하지 않는 사람과 이러한 명령 처리기의 오버 헤드는 컨테이너/서버 응용 프로그램 있지 않은 경우. CMainDoc 메시지 맵에 다음 항목을 추가 해야 합니다.  
  
```  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE,
    OnUpdatePasteMenu)  
ON_UPDATE_COMMAND_UI(ID_EDIT_PASTE_LINK,
    OnUpdatePasteLinkMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_LINKS,
    OnUpdateEditLinksMenu)  
ON_COMMAND(ID_OLE_EDIT_LINKS,
    COleDocument::OnEditLinks)  
ON_UPDATE_COMMAND_UI(ID_OLE_VERB_FIRST,
    OnUpdateObjectVerbMenu)  
ON_UPDATE_COMMAND_UI(ID_OLE_EDIT_CONVERT,
    OnUpdateObjectVerbMenu)  
ON_COMMAND(ID_OLE_EDIT_CONVERT,
    OnEditConvert)  
```  
  
 이 명령은 구현 중인 `COleDocument`,이 문서에 대 한 기본 클래스입니다.  
  
 이 OCLIENT 기능 OLE 컨테이너 응용 프로그램입니다. 항목 (OLE1 또는 OLE 2 개) 형식 삽입 하는 것이 불가능 합니다. 내부 활성화를 사용 하도록 설정 하는 데 필요한 코드 구현 되지 않으면 이후 항목 OLE1와 같은 많은 별도 창에서 편집 됩니다. 다음 섹션에서는 내부 편집 ("비주얼 편집" 라고도 함)을 사용 하도록 설정 하려면 필요에 따라 변경에 설명 합니다.  
  
## <a name="adding-visual-editing"></a>"비주얼 편집"을 추가합니다.  
 OLE의 가장 흥미로운 기능 중 하나에 내부 활성화 (또는 "비주얼 편집")입니다. 이 기능을 사용자에 대 한 보다 원활한 편집 인터페이스를 제공 하는 컨테이너의 사용자 인터페이스의 일부를 받으시겠습니까 서버 응용 프로그램이 있습니다. OCLIENT에 내부 활성화를 구현 하려면 몇 가지 특별 한 리소스를 몇 가지 추가 코드 뿐만 아니라 추가 해야 합니다. 이러한 리소스와 코드는 일반적으로 응용 프로그램 마법사에서 제공-실제로 "Container"를 지 원하는 새로운 응용 프로그램 마법사 응용 프로그램에서 직접 가져온가 여기에 코드의 대부분 합니다.  
  
 우선,에 내부 활성화 항목 없을 때 사용 되는 메뉴 리소스를 추가할 필요는. Visual c + +에서 IDR_OCLITYPE 리소스를 복사 하는 파일 및 창 팝업을 제외 하 고 모두 제거 하 여이 추가 메뉴 리소스를 만들 수 있습니다. 두 개의 구분 기호 막대를 나타내는 그룹을 분리 하 여 파일 및 창 팝업 사이 삽입 됩니다 (이 파일은 같아야: 파일 &#124; &#124; 창). 이러한 구분 기호 무엇을 의미 하 고 서버 및 컨테이너 메뉴를 병합 하는 방법에 대 한 자세한 내용은 "메뉴 및 리소스:: 메뉴 병합"의 참조 *OLE 2 클래스*합니다.  
  
 만든 이러한 메뉴를 사용 하는 후 프레임 워크 사항을 파악 해야 합니다. 호출 하 여 이렇게 `CDocTemplate::SetContainerInfo` 프로그램 InitInstance에 문서 템플릿 목록에 추가 하기 전에 문서 서식 파일에 대 한 합니다. 문서 서식 파일을 등록 하는 새 코드는 다음과 같습니다.  
  
```  
CDocTemplate* pTemplate = new CMultiDocTemplate(
    IDR_OLECLITYPE, 
    RUNTIME_CLASS(CMainDoc), 
    RUNTIME_CLASS(CMDIChildWnd), // standard MDI child frame  
    RUNTIME_CLASS(CMainView));

pTemplate->SetContainerInfo(IDR_OLECLITYPE_INPLACE);

AddDocTemplate(pTemplate);
```   
  
 IDR_OLECLITYPE_INPLACE 리소스는 Visual c + +에서 만든 특별 한 내부 리소스입니다.  
  
 내부 활성화를 사용 하려면 몇 가지 모두에서 변경 해야 하는 `CView` (CMainView) 파생 클래스와 `COleClientItem` 파생 클래스 (CRectItem). 이러한 재정의의 모든 응용 프로그램 마법사에서 제공 하 고 대부분의 구현은 기본 응용 프로그램 마법사 응용 프로그램에서 직접 제공 됩니다.  
  
 이 포트의 첫 번째 단계에서 내부 활성화를 재정의 하 여 완전히 비활성화 되었습니다 `COleClientItem::CanActivate`합니다. 내부 활성화를 허용 하도록이 재정의 제거 해야 합니다. NULL에 대 한 모든 호출에 전달 된 또한 `DoVerb` (는 그 중 두) 뷰를 제공 하는 내부 활성화에 필요한 때문에 있습니다. 내부 활성화를 완벽 하 게 구현 하려면 올바른 보기에 전달 하는 데 필요한는 `DoVerb` 호출 합니다. 이러한 호출 중 하나는 **CMainView::OnInsertObject**:  
  
```  
pItem->DoVerb(OLEIVERB_SHOW, this);
```  
  
 에 다른 **CMainView::OnLButtonDblClk**:  
  
```  
m_pSelection->DoVerb(OLEIVERB_PRIMARY, this);
```  
  
 재정의할 필요는 `COleClientItem::OnGetItemPosition`합니다. 이 서버를 위치에 알려 항목이 활성화 될 때 해당 창을 컨테이너의 창을 기준으로 설정 합니다. OCLIENT, 구현은 매우 간단 합니다.  
  
```  
void CRectItem::OnGetItemPosition(CRect& rPosition)  
{  
    rPosition = m_rect;  
}  
```  
  
 대부분의 서버는 "내부 크기 조정 합니다." 이라는 구현 따라서 서버 창을 크기가 정 해지고 사용자가 항목을 편집 하는 동안 가상 컴퓨터 이동할 수 있습니다. 컨테이너 이동 하거나 일반적으로 창 크기 조정에 영향을 줍니다 컨테이너 문서 자체 내 크기와 위치 하므로이 작업에 참여 해야 합니다. OCLIENT에 대 한 구현을 m_rect 새 위치와 크기를 사용 하 여 유지 관리 하는 내부 사각형을 동기화 합니다.  
  
```  
BOOL CRectItem::OnChangeItemPosition(const CRect& rectPos)  
{  
    ASSERT_VALID(this);

 
    if (!COleClientItem::OnChangeItemPosition(rectPos))  
    return FALSE;  
 
    Invalidate();
m_rect = rectPos;  
    Invalidate();
GetDocument()->SetModifiedFlag();

 
    return TRUE;  
}  
```  
  
 이 시점에서 내부 활성화 하 고, 활성화 된 경우 해당 항목을 이동 및 크기 조정을 처리 하는 항목 수 있도록 충분 한 코드는 없지만 없는 코드를 편집 세션을 종료할 수 있습니다. 하지만 일부 서버는이 기능 자체 esc 키를 처리 하 여, 것이 좋습니다 컨테이너 항목을 비활성화 하는 두 가지를 제공: 해당 항목을 외부를 클릭 하 여 다음을 수행 합니다 (1) 및 (2) 키를 눌러 이스케이프 합니다.  
  
 ESC 키에 대 한 명령에 VK_ESCAPE 키를 매핑하는 Visual c + + 액셀러레이터 키를 추가, ID_CANCEL_EDIT 리소스에 추가 됩니다. 이 명령의 처리기는 다음과 같습니다.  
  
```  
// The following command handler provides the standard  
// keyboard user interface to cancel an in-place  
// editing session.void CMainView::OnCancelEdit()  
{ *// Close any in-place active item on this view.  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->Close();
ASSERT(GetDocument()->GetInPlaceActiveItem(this) == NULL);

}  
```  
  
 다음 코드의 시작 부분에 추가 하면 사용자 항목 외부 클릭할 수 있는 경우를 처리 하려면 **CMainView::SetSelection**:  
  
```  
if (pNewSel != m_pSelection || pNewSel == NULL)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& pActiveItem != pNewSel)  
    pActiveItem->Close();

} 
 
```  
  
 내부 활성화 항목을 사용 하는 경우 포커스가 있어야 합니다. 대/소문자 인지 확인 하려면 포커스 전송할 때는 항상 활성 항목으로 보기 포커스를 받을 때을 OnSetFocus 처리:  
  
```  
// Special handling of OnSetFocus and OnSize are required   
// when an object is being edited in-place.  
void CMainView::OnSetFocus(CWnd* pOldWnd)  
{  
    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL&& 
    pActiveItem->GetItemState() == COleClientItem::activeUIState)  
 { *// need to set focus to this item if it is same view  
    CWnd* pWnd = pActiveItem->GetInPlaceWindow();
if (pWnd != NULL)  
 {  
    pWnd->SetFocus();
*// don't call the base class  
    return; 
 }  
 }  
 
    CView::OnSetFocus(pOldWnd);

} 
```  
  
 뷰 크기를 조정 하면 활성 항목으로 클리핑 사각형 변경 되었음을 알리기 위해 필요 합니다. 에 대 한 처리기를 제공 하는이 작업을 수행 하려면 `OnSize`:  
  
```  
void CMainView::OnSize(UINT nType,
    int cx,
    int cy)  
{  
    CView::OnSize(nType,
    cx,
    cy);

    COleClientItem* pActiveItem = 
    GetDocument()->GetInPlaceActiveItem(this);

 if (pActiveItem != NULL)  
    pActiveItem->SetItemRects();

} 
```  
  
## <a name="case-study-hiersvr-from-mfc-20"></a>사례 연구: HIERSVR MFC 2.0에서  
 [HIERSVR](../visual-cpp-samples.md) 도 MFC 2.0에 포함 된 및 OLE MFC/OLE1를 구현 합니다. 이 노트는 기준인이 응용 프로그램 처음 변환 MFC/OLE 2 클래스를 사용 하는 단계를 간략하게 설명 합니다. 초기 포트 MFC/OLE 2 클래스 이해를 돕기 위해 완료 된 후에 다양 한 기능이 추가 되었습니다. 이러한 기능은 다루지 않습니다. 이러한 고급 기능에 대 한 자세한 내용은 샘플 자체를 참조 하십시오.  
  
> [!NOTE]
>  컴파일러 오류 및 단계별 프로세스는 Visual c + + 2.0으로 만들어졌습니다. Visual c + + 4.0 특정 오류 메시지 및 위치 변경 수 있습니다 하지만 개념 정보 유효한 상태를 유지 합니다.  
  
## <a name="getting-it-up-and-running"></a>해당 시작 및 실행  
 MFC/OLE로 HIERSVR 샘플 포트를 사용 하는 접근 방식은 빌드하고 발생 시키는 확실 한 컴파일러 오류를 수정 하 여 먼저입니다. MFC 2.0에서 HIERSVR 샘플을 사용 하 고이 버전의 MFC에서 컴파일 오류 수 (있더라도 OCLIENT 샘플을 여러 개)를 해결 되지 않았는지를 찾을 수 있습니다. 에 일반적으로 수행 하는 순서에서 오류에 대 한 설명은 다음과 같습니다.  
  
## <a name="compile-and-fix-errors"></a>컴파일 및 오류 수정  
  
```  
\hiersvr\hiersvr.cpp(83) : error C2039: 'RunEmbedded' : is not a member of 'COleTemplateServer'  
```  
  
 이 첫 번째 오류에 훨씬 더 큰 문제가 지적는 `InitInstance` 서버에 대 한 함수입니다. OLE 서버에 필요한 초기화 하는 가장 중요 한 MFC/OLE1 응용 프로그램을 실행할 수 있도록 해야 합니다. 변경 중 하나입니다. 작업을 수행 하는 것이 가장 좋습니다 OLE 서버에 대 한 마법사에서는 확인 되며 적절 하 게 코드를 수정 합니다. 다음은 몇 가지 사항을 염두에서에 둬야입니다.  
  
 OLE 라이브러리를 호출 하 여 초기화 해야 하는 **AfxOleInit**  
  
 서버 리소스 핸들 및으로 설정할 수 없는 런타임 클래스 정보를 설정 하려면 문서 템플릿 개체에 SetServerInfo 호출는 `CDocTemplate` 생성자입니다.  
  
 응용 프로그램의 주 창 상관 명령줄에 있는 경우에 표시 하지 마십시오.  
  
 해야 합니다는 **GUID** 문서에 대 한 합니다. 문서 형식 (128 비트)에 대 한 고유 식별자입니다. 응용 프로그램 마법사에서 구독을 하나 만들어집니다-여기에서 설명 하는 기술을 사용 하는 경우 새 생성 하는 응용 프로그램 마법사에서 서버 응용 프로그램에서 새 코드를 복사 하면 단순히 "암호를 훔칠 수" 해당 응용 프로그램의 GUID입니다. 그렇지 않은 경우는 GUIDGEN를 사용할 수 있습니다. EXE 유틸리티 BIN 디렉터리에 있습니다.  
  
 "연결" 하는 데 필요한 프로그램 `COleTemplateServer` 개체를 호출 하 여 문서 서식 파일 `COleTemplateServer::ConnectTemplate`합니다.  
  
 응용 프로그램이 독립형 실행 될 때 시스템 레지스트리를 업데이트 합니다. 이 이렇게 하면 사용자가 고 있습니다. 응용 프로그램에 대 한 EXE를 새 위치에서 실행 하는 새 위치를 가리키도록 Windows 시스템 등록 데이터베이스를 업데이트 합니다.  
  
 에 대 한 마법사에서는에 따라 이러한 변경 내용이 모두 적용 한 후 `InitInstance`, `InitInstance` (및 관련 GUID) HIERSVR 다음과 같이 참조 해야 합니다.  
  
```  
// this is the GUID for HIERSVR documents  
static const GUID BASED_CODE clsid = 
 { 0xA0A16360L,
    0xC19B,
    0x101A, { 0x8C,
    0xE5,
    0x00,
    0xDD,
    0x01,
    0x11,
    0x3F,
    0x12 } };  
 
/////////////////////////////////////////////////////////////////////////////  
// COLEServerApp initialization  
 
BOOL COLEServerApp::InitInstance()  
{ *// OLE 2 initialization  
    if (!AfxOleInit())  
 {  
    AfxMessageBox("Initialization of the OLE failed!");

    return FALSE;  
 }  
 *// Standard initialization  
    LoadStdProfileSettings();

// Load standard INI file options   
 *// Register document templates  
    CDocTemplate* pDocTemplate;  
    pDocTemplate = new CMultiDocTemplate(IDR_HIERSVRTYPE,  
    RUNTIME_CLASS(CServerDoc), 
    RUNTIME_CLASS(CMDIChildWnd), 
    RUNTIME_CLASS(CServerView));

 pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB);

    AddDocTemplate(pDocTemplate);

 *// create main MDI Frame window  
    CMainFrame* pMainFrame = new CMainFrame;  
    if (!pMainFrame->LoadFrame(IDR_MAINFRAME))  
    return FALSE;  
    m_pMainWnd = pMainFrame;  
 
    SetDialogBkColor();
*// gray look  
 *// enable file manager drag/drop and DDE Execute open  
    m_pMainWnd->DragAcceptFiles();
EnableShellOpen();

 
    m_server.ConnectTemplate(clsid,
    pDocTemplate,
    FALSE);

    COleTemplateServer::RegisterAll();

 *// try to launch as an OLE server  
    if (RunEmbedded())  
 { *// "short-circuit" initialization -- run as server!  
    return TRUE;  
 }  
    m_server.UpdateRegistry();
RegisterShellFileTypes();

 *// not run as OLE server,
    so show the main window  
    if (m_lpCmdLine[0] == '\0')  
 { *// create a new (empty) document  
    OnFileNew();

 }  
    else 
 { *// open an existing document  
    OpenDocumentFile(m_lpCmdLine);

 }  
 
    pMainFrame->ShowWindow(m_nCmdShow);

 pMainFrame->UpdateWindow();

 
    return TRUE;  
}  
```  
  
 위의 코드는 새 리소스 ID IDR_HIERSVRTYPE_SRVR_EMB 참조 하는지 확인할 수 있습니다. 다른 컨테이너에 포함 된 문서를 편집할 때 사용 되는 메뉴 리소스입니다. MFC/OLE1 포함된 된 항목을 편집 관련 메뉴 항목은 즉석에서 수정 되었습니다. 파일 기반 문서를 편집 하는 대신 포함된 된 항목을 편집할 때 완전히 다른 메뉴 구조를 사용 하면 훨씬 쉽게이 두 가지 별도 모드에 대 한 다른 사용자 인터페이스를 제공할 수 있습니다. 나중에 볼 수 있듯이 완전히 별도 메뉴 리소스는 포함 된 개체 전체를 편집할 때 사용 됩니다.  
  
 이 리소스를 만들려면 리소스 스크립트는 Visual c + +에 로드 되 고 기존 IDR_HIERSVRTYPE 메뉴 리소스를 복사 합니다. (이 응용 프로그램 마법사를 사용 하는 동일한 명명 규칙) IDR_HIERSVRTYPE_SRVR_EMB 새 리소스를 이름을 바꿉니다. 다음에 "파일 업데이트"; "파일 저장"를 변경 명령 ID를 지정한 **ID_FILE_UPDATE**합니다. "파일 복사본으로 저장"; "다른 이름으로 저장"을 변경할 수도 명령 ID를 지정한 **ID_FILE_SAVE_COPY_AS**합니다. 프레임 워크에는 두이 명령은 모두의 구현을 제공합니다.  
  
```  
\hiersvr\svritem.h(60) : error C2433: 'OLESTATUS' : 'virtual' not permitted on data declarations  
\hiersvr\svritem.h(60) : error C2501: 'OLESTATUS' : missing decl-specifiers  
\hiersvr\svritem.h(60) : error C2146: syntax error : missing ';' before identifier 'OnSetData'  
\hiersvr\svritem.h(60) : error C2061: syntax error : identifier 'OLECLIPFORMAT'  
\hiersvr\svritem.h(60) : error C2501: 'OnSetData' : missing decl-specifiers  
```  
  
 재정의에서 발생 한 오류가의 여러 가지 `OnSetData`이므로 참조 하는 **OLESTATUS** 유형입니다. **OLESTATUS** OLE1 반환 된 오류 방법 이었습니다. 이러한 사항이 변경 `HRESULT` OLE 2에서는 MFC 일반적으로 변환 합니다. 하지만 `HRESULT` 에 `COleException` 오류가 포함 된 합니다. 이 특정 경우의 재정의 `OnSetData` 이므로 더 이상 필요에 따라는 가장 쉬운 방법은 제거 합니다.  
  
```  
\hiersvr\svritem.cpp(30) : error C2660: 'COleServerItem::COleServerItem' : function does not take 1 parameters  
```  
  
 `COleServerItem` 생성자는 추가 'BOOL' 매개 변수를 사용 합니다. 이 플래그는 메모리 관리에서 수행 되는 방법 결정는 `COleServerItem` 개체입니다. 프레임 워크를 TRUE로 설정 하 여 이러한 개체의 메모리 관리 처리-더 이상 필요 없는 경우 삭제 합니다. 사용 하 여 HIERSVR **CServerItem** (에서 파생 된 `COleServerItem`)이이 플래그 값을 FALSE로 설정 합니다 원시 데이터의 일부로 개체입니다. 따라서 HIERSVR을 각 서버 항목을 삭제 하는 경우 확인할 수 있습니다.  
  
```  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
\hiersvr\svritem.cpp(44) : error C2259: 'CServerItem' : illegal attempt to instantiate abstract class  
```  
  
 이러한 오류에서 알 수 있듯이는 다음과 같은 몇 가지 ' 순수 가상 ' 함수에서 CServerItem 재정의 하지 않은입니다. 대개 OnDraw의 매개 변수 목록입니다.이 변경 되었다는 사실만 여 원인입니다. 이 오류를 해결 하려면 변경 **cserveritem:: Ondraw** 다음과 같습니다 (뿐만 아니라 svritem.h에서 선언):  
  
```  
BOOL CServerItem::OnDraw(CDC* pDC,
    CSize& rSize)  
{ *// request from OLE to draw node  
    pDC->SetMapMode(MM_TEXT);

// always in pixels  
    return DoDraw(pDC,
    CPoint(0,
    0),
    FALSE);

}  
```  
  
 새 매개 변수 'rSize'입니다. 이렇게 하면 편리 하 게 하는 경우 그리기, 개체의 크기를 채울 수 있습니다. 이 크기에 있어야 합니다. **HIMETRIC**합니다. 이 경우 것은 불편할이 값을 채울 프레임 워크에서 호출 되므로 `OnGetExtent` 범위를 검색할 수 있습니다. 실행 되도록이 위해 구현 해야 `OnGetExtent`:  
  
```  
BOOL CServerItem::OnGetExtent(DVASPECT dwDrawAspect,
    CSize& rSize)  
{  
    if (dwDrawAspect != DVASPECT_CONTENT)  
    return COleServerItem::OnGetExtent(dwDrawAspect,
    rSize);

 
    rSize = CalcNodeSize();
return TRUE;  
}  
 
\hiersvr\svritem.cpp(104) : error C2065: 'm_rectBounds' : undeclared identifier  
\hiersvr\svritem.cpp(104) : error C2228: left of '.SetRect' must have class/struct/union type  
\hiersvr\svritem.cpp(106) : error C2664: 'void __pascal __far DPtoLP(struct ::tagPOINT __far *,
    int)__far const ' : cannot convert parameter 1 from 'int __far *' to 'struct ::tagPOINT __far *'  
```  
  
 항목 크기 변환할 CServerItem::CalcNodeSize 함수에서 **HIMETRIC** 에 저장 하 고 **m_rectBounds**합니다. 문서화 되지 않은 '**m_rectBounds**' 소속 `COleServerItem` 존재 하지 않는 (부분적으로 대체 되었습니다 `m_sizeExtent`, OLE 2에서이 멤버에 보다 약간 다른 사용 하지만 **m_rectBounds**OLE1에서). 설정 하는 대신는 **HIMETRIC** 크기가 멤버 변수로 것 반환할 수 있습니다. 반환이 값은 사용 `OnGetExtent`이전에 구현 합니다.  
  
```  
CSize CServerItem::CalcNodeSize()  
{  
    CClientDC dcScreen(NULL);

 
    m_sizeNode = dcScreen.GetTextExtent(m_strDescription,  
    m_strDescription.GetLength());

 m_sizeNode += CSize(CX_INSET* 2,
    CY_INSET* 2);

 *// set suggested HIMETRIC size  
    CSize size(m_sizeNode.cx,
    m_sizeNode.cy);

    dcScreen.SetMapMode(MM_HIMETRIC);

 dcScreen.DPtoLP(&size);

    return size;  
}  
```  
  
 CServerItem 재정의 **COleServerItem::OnGetTextData**합니다. 이 함수는 MFC/OLE에서 사용 되지 않는 하 고 다른 메커니즘으로 대체 됩니다. MFC 3.0 버전의 MFC OLE 샘플 [HIERSVR](../visual-cpp-samples.md) 재정의 하 여이 기능을 구현 `COleServerItem::OnRenderFileData`합니다. 이 기능은 OnGetTextData 재정의 제거할 수 있는이 기본 포트에 대 한 중요 하지 않습니다.  
  
 해결 되지 svritem.cpp에 더 많은 오류가 있습니다. "실제" 오류가 없는 — 이전 오류로 인해 발생 한 오류만 합니다.  
  
```  
\hiersvr\svrview.cpp(325) : error C2660: 'CopyToClipboard' : function does not take 2 parameters  
```  
  
 `COleServerItem::CopyToClipboard` 더 이상 'bIncludeNative' 플래그를 지원합니다. 원시 데이터 (데이터 서버 항목의 Serialize 함수에 의해 기록)이 첫 번째 매개 변수를 제거 하므로 항상 복사 됩니다. 또한 `CopyToClipboard` FALSE를 반환 하는 대신 오류가 발생할 때 예외가 throw 됩니다. 다음과 같이 CServerView::OnEditCopy에 대 한 코드를 변경 합니다.  
  
```  
void CServerView::OnEditCopy()  
{  
    if (m_pSelectedNode == NULL)  
    AfxThrowNotSupportedException();

 
    TRY 
 {  
    m_pSelectedNode->CopyToClipboard(TRUE);

 }  
    CATCH_ALL(e) 
 {  
    AfxMessageBox("Copy to clipboard failed");

 }  
    END_CATCH_ALL 
}  
```  
  
 보다 OCLIENT의 동일한 버전에 대 한 HIERSVR의 MFC 2.0 버전의 컴파일에서 발생 한 더 많은 오류가 가지가 있었지만 개가 실제로 더 적은 변경 합니다.  
  
 이 시점에서 HIERSVR을 및 연결 컴파일하고 구현 하는 내부 편집 기능을 하지 않고 OLE 서버로 작동 합니다.  
  
## <a name="adding-visual-editing"></a>"비주얼 편집"을 추가합니다.  
 "비주얼 편집" (또는 내부 활성화)이 서버 응용 프로그램을 추가 하려면 가지만 몇 가지의 주의 해야 합니다.  
  
-   특별 한 메뉴 리소스를은 항목이 내부 활성화 되었을 때 사용할 수 해야 합니다.  
  
-   이 응용 프로그램에는 도구 모음, 되므로 있는 도구 모음에 메뉴 명령이 서버에서 사용할 수 있는 (위에서 언급 한 메뉴 리소스와 같음)와 일치 하도록 일반 도구 모음의 하위 집합만 필요 합니다.  
  
-   파생 된 새 클래스가 필요 하면 `COleIPFrameWnd` 내부 사용자 인터페이스를 제공 하는 (과 거의 동일한에서 파생 된 CMainFrame `CMDIFrameWnd`, MDI 사용자 인터페이스를 제공).  
  
-   이러한 특별 한 리소스 및 클래스에 대 한 프레임 워크를 지시 해야 합니다.  
  
 메뉴 리소스를 쉽게 만들 수 있습니다. Visual c + + 실행, 메뉴 리소스 IDR_HIERSVRTYPE IDR_HIERSVRTYPE_SRVR_IP 라는 메뉴 리소스를 복사 합니다. 편집 하며 도움말 메뉴 팝업만 남겨진다는 메뉴를 수정 합니다. 두 개의 구분 기호 사이 편집 및 도움말 메뉴에서 메뉴에 추가 (같이 표시 됩니다: 편집 &#124; &#124; 도움말). 이러한 구분 기호 무엇을 의미 하 고 서버 및 컨테이너 메뉴를 병합 하는 방법에 대 한 자세한 내용은 "메뉴 및 리소스:: 메뉴 병합"의 참조 *OLE 2 클래스*합니다.  
  
 "서버" 옵션을 선택 하 여 새로 생성 하는 응용 프로그램 마법사에서 응용 프로그램에서 하나를 복사 하 여 도구 모음에서 하위 집합에 대 한 비트맵을 쉽게 만들 수 있습니다. 이 비트맵 Visual c + +로 가져올 수 있습니다. ID의 IDR_HIERSVRTYPE_SRVR_IP 비트맵을 지정 해야 합니다.  
  
 클래스에서 파생 된 `COleIPFrameWnd` 서버 지원 및으로 생성 하는 응용 프로그램 마법사에서 응용 프로그램에서 복사할 수 있습니다. IPFRAME 두 파일을 복사 합니다. CPP 및 IPFRAME 합니다. H 프로젝트에 추가 합니다. 다음 사항을 확인는 `LoadBitmap` 호출 IDR_HIERSVRTYPE_SRVR_IP, 이전 단계에서 만든 비트맵을 가리킵니다.  
  
 새 리소스 및 클래스를 모두 생성, 했으므로 이러한에 대해 알고 (및이 응용 프로그램을 지금 내부 편집을 지원 하는지 알고) 프레임 워크 있도록 필요한 코드를 추가 합니다. 몇 가지 더 많은 매개 변수를 추가 하면 됩니다는 `SetServerInfo` 에서 호출 된 `InitInstance` 함수:  
  
```  
pDocTemplate->SetServerInfo(IDR_HIERSVRTYPE_SRVR_EMB,  
    IDR_HIERSVRTYPE_SRVR_IP,
    RUNTIME_CLASS(CInPlaceFrame));
```  
  
 내부에서 실행할 준비가 되었습니다도 내부 활성화를 지 원하는 모든 컨테이너에 있습니다. 그러나 코드에 아직 해결 사소한 버그 하나 있습니다. HIERSVR은 사용자가 마우스 오른쪽 단추를 누를 때 표시 되는 상황에 맞는 메뉴를 지원 합니다. 이 메뉴에는 HIERSVR 완전히 열고 하지만 포함 전체를 편집 하는 경우 작동 하지 않는 경우 작동 합니다. 이유는 CServerView::OnRButtonDown에 코드의이 한 줄 고정할 수 있습니다.  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetApp()->m_pMainWnd);
```  
  
 에 대 한 참조를 확인할 **AfxGetApp() m_pMainWnd->** 합니다. 서버가 활성화 될 때 주 창 및 m_pMainWnd 설정 되어 있으며 일반적으로 표시 되지 않습니다. 또한이 창 참조 하는 *주* 응용 프로그램 창, 서버를 완벽 하 게 표시 되는 MDI 프레임 창 열기 또는 독립 실행형 실행 합니다. 활성 프레임이 창을 참조 하지 않는-때 내부 활성화 되는 프레임에서 파생 된 창 `COleIPFrameWnd`합니다. 내부 편집,이 버전의 MFC는 새 함수를 추가 하는 경우에 올바른 활성 창 하기 위해 `AfxGetMainWnd`합니다. 대신이 함수를 사용 해야 하는 일반적으로 **AfxGetApp() m_pMainWnd->** 합니다. 이 코드는 다음과 같이 변경 해야 합니다.  
  
```  
pMenu->TrackPopupMenu(TPM_CENTERALIGN | TPM_RIGHTBUTTON,  
    point.x,
    point.y,
    AfxGetMainWnd());
```  
  
 이제 OLE 서버 기능에 내부 활성화에 대 한 최소한으로 사용 하도록 설정 해야 합니다. 하지만 MFC/OLE1에서 사용할 수 있었던 MFC/OLE 2로 사용할 수 있는 기능이 많이 여전히 있습니다. 기능을 구현 하는 것이 좋습니다에 자세한 내용은 HIERSVR 샘플을 참조 하십시오. HIERSVR 구현 하는 기능 중 일부는 다음과 같습니다.  
  
-   컨테이너에 대해 true WYSISYG 동작에 대 한 확대 합니다.  
  
-   끌어 / 삭제 하 고 사용자 지정 클립보드 형식입니다.  
  
-   선택 항목으로 컨테이너 창을 스크롤하여 변경 됩니다.  
  
 MFC 3.0에서 HIERSVR 샘플 약간 다른 디자인을 사용 하 여 해당 서버 항목에 대 한 합니다. 메모리를 절약 고 링크를 더 융통성이 있습니다. HIERSVR의 2.0 버전으로는 트리의 각 노드에 *동등* `COleServerItem`합니다. `COleServerItem` 이러한 각 노드를 반드시 필요한 것 보다 좀 더 오버 헤드를 전달 하지만 `COleServerItem` 활성 각 링크에 대해 필요 합니다. 그러나 대부분의 경우 사항이 매우 적은 활성 링크 지정된 된 시간에 있습니다. 보다 효율적인이 수행 하려면이 버전의 MFC에서 HIERSVR 구분에서 노드는 `COleServerItem`합니다. 두 CServerNode 있기 및 **CServerItem** 클래스입니다. **CServerItem** (에서 파생 된 `COleServerItem`) 필요에 따라 생성 됩니다. 컨테이너 (또는 컨테이너)에 해당 특정 노드의 해당 특정 링크를 사용 하 여 중지 된 CServerNode와 연결 된 CServerItem 개체 삭제 됩니다. 이 디자인 더 효율적이 고 보다 유연한입니다. 유동성이 처리할 여러 개의 링크를 선택 하는 경우 제공 됩니다. HIERSVR의 이러한 두 버전 모두에서 다중 선택을 지원 하지만 것이 훨씬 쉽게 추가할 (및 이러한 선택 항목에 대 한 링크를 지원 하기 위해) HIERSVR의 MFC 3.0 버전과 이후는 `COleServerItem` 원시 데이터에서 구분 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

