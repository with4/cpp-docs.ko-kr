---
title: "TN071: MFC IOleCommandTarget 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IOleCommandTarget
dev_langs:
- C++
helpviewer_keywords:
- TN071 [MFC]
- IOleCommandTarget interface [MFC]
ms.assetid: 3eef571e-6357-444d-adbb-6f734a0c3161
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43f97774036c42fa0f681a65e0a335f944daf09c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn071-mfc-iolecommandtarget-implementation"></a>TN071: MFC IOleCommandTarget 구현
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 `IOleCommandTarget` 개체와 해당 컨테이너를 서로 명령 디스패치 인터페이스를 사용 합니다. 예를 들어 개체의 도구 모음 명령에 대 한 단추와 같은 포함할 수 **인쇄**, **인쇄 미리 보기**, **저장**, `New`, 및 **확대/축소**. 이러한 개체를 지 원하는 컨테이너에 포함 된 경우 `IOleCommandTarget`, 개체 수 단추를 사용 하도록 설정 하 고 사용자를 클릭 하면 해당 처리에 대 한 컨테이너에 명령을 전달 합니다. 통해 명령을 전송 하 여이 요청을 만들 수는 컨테이너 자체를 인쇄 하려면 포함 된 개체를 려는 `IOleCommandTarget` 포함된 된 개체의 인터페이스입니다.  
  
 `IOleCommandTarget`서버에서 메서드를 호출 하는 클라이언트에서 사용 된다는 같은 자동화 인터페이스가입니다. 그러나를 사용 하 여 `IOleCommandTarget` 프로그래머 사용 하 여 일반적으로 리소스를 소모할 필요가 없으므로 자동화 인터페이스를 통해 호출의 오버 헤드를 줄여 `Invoke` 방식의 `IDispatch`합니다.  
  
 Mfc에서 `IOleCommandTarget` 인터페이스 액티브 문서 컨테이너 서버에 명령을 디스패치할 수 있도록 액티브 문서 서버에서 사용 됩니다. 액티브 문서 서버 클래스 `CDocObjectServerItem`, MFC의 인터페이스 맵을 사용 하 여 (참조 [TN038: MFC/OLE IUnknown 구현](../mfc/tn038-mfc-ole-iunknown-implementation.md))을 구현 하는 `IOleCommandTarget` 인터페이스입니다.  
  
 `IOleCommandTarget`또한에서 구현 되는 **COleFrameHook** 클래스입니다. **COleFrameHook** 가 문서화 되지 않은 MFC 클래스의 내부 프레임 창 기능을 구현 하는 컨테이너를 편집 합니다. **COleFrameHook** 또한 MFC 인터페이스 맵을 사용 하 여 구현 하는 `IOleCommandTarget` 인터페이스입니다. **COleFrameHook**의 구현의 `IOleCommandTarget` OLE 명령을 전달 `COleDocObjectItem`-액티브 문서 컨테이너를 파생 합니다. 따라서 모든 MFC 액티브 문서 컨테이너를 포함 된 액티브 문서 서버에서 메시지를 받을 수 있습니다.  
  
## <a name="mfc-ole-command-maps"></a>MFC OLE 명령 맵  
 MFC 개발자 활용할 수 `IOleCommandTarget` 를 사용 하 여 MFC OLE 지도 명령입니다. OLE 명령 맵 비슷합니다 OLE 명령 명령 맵을 포함 하는 클래스의 멤버 함수에 매핑할 사용할 수 있기 때문에 메시지 맵. 이 작업을 하려면 매크로 처리할 명령, OLE 명령 및 명령 ID의 OLE 명령 그룹을 지정 하려면 명령 맵에 배치 된 [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) OLE 명령의 받을 때 보낼 메시지입니다. 또한 MFC는 표준 OLE 명령에 대 한 다양 한 미리 정의 된 매크로 제공합니다. 표준 OLE의 목록에 대 한 명령을 위해 원래 디자인 된 Microsoft Office 응용 프로그램과 함께 사용할 docobj.h에 정의 된 OLECMDID 열거형을 참조 하십시오.  
  
 OLE 명령 OLE 명령 맵을 포함 하는 MFC 응용 프로그램에서 수신 되 면 MFC OLE 명령 맵의 응용 프로그램의 요청 된 명령에 대 한 명령 ID와 명령 그룹을 찾을 하려고 합니다. 일치 하는 항목이 없는 경우는 **WM_COMMAND** 메시지 id가 요청 된 명령이 명령 맵이 포함 된 응용 프로그램에 디스패치 됩니다. (설명 참조 `ON_OLECMD` 아래.) 이러한 방식으로 응용 프로그램에 디스패치할 OLE 명령으로 설정 **WM_COMMAND** MFC에서 메시지입니다. **WM_COMMAND** MFC 표준을 사용 하 여 응용 프로그램의 메시지 맵을 통해 메시지가 라우팅되 다음 [명령 라우팅](../mfc/command-routing.md) 아키텍처.  
  
 메시지 맵 달리 MFC OLE 명령 맵 classwizard 함께 사용 하 여 지원 되지 않습니다. MFC 개발자 OLE 명령 맵 지원 및 OLE 명령 맵 항목을 수동으로 추가 해야 합니다. OLE 명령 맵에 추가할 수에 모든 클래스에서 MFC 액티브 문서 서버는 **WM_COMMAND** 액티브 문서 컨테이너에에 내부 활성화는 한 번에 메시지 라우팅 체인입니다. 이러한 클래스에서 파생 된 응용 프로그램의 클래스에는 [CWinApp](../mfc/reference/cwinapp-class.md), [CView](../mfc/reference/cview-class.md), [CDocument](../mfc/reference/cdocument-class.md), 및 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)합니다. 액티브 문서 컨테이너에 OLE 명령 맵만 추가할 수는 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)-클래스를 파생 합니다. 또한 액티브 문서 컨테이너에는 **WM_COMMAND** 발송에서 메시지 맵을 메시지는 `COleDocObjectItem`-파생 클래스입니다.  
  
## <a name="ole-command-map-macros"></a>OLE 명령 맵 매크로  
 다음 매크로 사용 하 여 명령 맵 기능 클래스에 추가 하려면:  
  
```  
 
DECLARE_OLECMD_MAP ()  
 
```  
  
 이 매크로 (일반적으로 헤더 파일)에 명령 맵을 포함 하는 클래스의 클래스 선언에서 이동 합니다.  
  
```  
 
BEGIN_OLECMD_MAP(
theClass  ,   baseClass)  
 
```  
  
 `theClass`  
 명령 맵을 포함 하는 클래스의 이름입니다.  
  
 `baseClass`  
 명령 맵을 포함 하는 클래스의 기본 클래스의 이름입니다.  
  
 이 매크로 명령 맵의 시작을 표시 합니다. 명령 맵을 포함 하는 클래스에 대 한 구현 파일에서이 매크로 사용 합니다.  
  
```  
 
END_OLECMD_MAP()  
 
```  
  
 이 매크로 명령 맵의 끝을 표시 합니다. 명령 맵을 포함 하는 클래스에 대 한 구현 파일에서이 매크로 사용 합니다. 이 매크로 항상 수행 해야 합니다는 **BEGIN_OLECMD_MAP** 매크로입니다.  
  
```  
 
ON_OLECMD(
pguid  ,   
olecmdid  ,
    id)  
 
```  
  
 `pguid`  
 OLE 명령 명령 그룹의 GUID에 대 한 포인터입니다. 이 매개 변수는 **NULL** 표준 OLE 명령 그룹에 대 한 합니다.  
  
 *olecmdid*  
 OLE 호출할 명령의 명령 ID입니다.  
  
 `id`  
 ID는 **WM_COMMAND** 메시지를이 OLE 명령을 호출할 때 명령 맵이 포함 된 응용 프로그램에 보냅니다.  
  
 사용 하 여는 `ON_OLECMD` OLE에 대 한 항목을 추가 하려면 명령 맵에서 매크로 처리할 명령입니다. 변환지 것입니다 OLE 명령의 받을 때 지정 된 **WM_COMMAND** 메시지 보내기 및 표준 MFC 명령 라우팅 아키텍처를 사용 하 여 응용 프로그램의 메시지 맵을 통해 라우팅됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 처리 하는 MFC 액티브 문서 서버에 OLE 명령 처리 기능을 추가 하는 [OLECMDID_PRINT](http://msdn.microsoft.com/library/windows/desktop/ms691264) OLE 명령입니다. 이 예에서는 가정 액티브 문서 서버는 MFC 응용 프로그램을 생성 하려면 응용 프로그램 마법사를 사용 합니다.  
  
1.  사용자 `CView`-파생 클래스의 헤더 파일에서 추가 `DECLARE_OLECMD_MAP` 클래스 선언에는 매크로입니다.  
  
    > [!NOTE]
    >  사용 하 여는 `CView`-액티브 문서 서버에 있는의 클래스 중 하나 이기 때문에 파생 클래스는 **WM_COMMAND** 메시지 라우팅 체인입니다.  
  
 ```  
    class CMyServerView : public CView  
 {  
    protected: // create from serialization only  
    CMyServerView();
DECLARE_DYNCREATE(CMyServerView)  
    DECLARE_OLECMD_MAP() 
 . . .  
 };  
 ```  
  
2.  에 대 한 구현 파일에는 `CView`-파생 클래스를 추가 `BEGIN_OLECMD_MAP` 및 `END_OLECMD_MAP` 매크로:  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView, CView)  
 
    END_OLECMD_MAP() 
 ```  
  
3.  표준 OLE 인쇄 명령을 처리 하려면 추가 [ON_OLECMD](reference/message-map-macros-mfc.md#on_olecmd) 표준 인쇄 명령에 대 한 OLE 명령 ID를 지정 하 여 명령 맵 매크로 및 **ID_FILE_PRINT** 에 대 한는 **WM_COMMAND**  Id입니다. **ID_FILE_PRINT** 표준 MFC 응용 프로그램 마법사에서 생성 된 응용 프로그램에서 사용 하는 인쇄 명령 ID입니다.  
  
 ```  
    BEGIN_OLECMD_MAP(CMyServerView,
    CView)  
    ON_OLECMD(NULL,
    OLECMDID_PRINT,
    ID_FILE_PRINT) 
    END_OLECMD_MAP() 
 ```  
  
 대신에 사용할 수 없습니다 afxdocob.h를에 정의 된 표준 OLE 명령 매크로 중 하나는 `ON_OLECMD` 매크로 때문에 **OLECMDID_PRINT** 표준 OLE 명령 ID입니다. `ON_OLECMD_PRINT` 매크로와 동일한 작업을 수행 합니다는 `ON_OLECMD` 위에 표시 된 매크로입니다.  
  
 컨테이너 응용 프로그램에서이 서버를 전송 하는 경우는 **OLECMDID_PRINT** 는 서버를 통해 명령을 `IOleCommandTarget` 인터페이스, 명령 처리기를 인쇄 하는 MFC 응용 프로그램을 인쇄 하기 위해 서버 프로그램이 서버에서 호출 됩니다. 위의 단계에서 추가 된 인쇄 명령을 호출 하는 액티브 문서 컨테이너의 코드는이 같습니다.  
  
```  
void CContainerCntrItem::DoOleCmd()  
{  
    IOleCommandTarget *pCmd = NULL;  
    HRESULT hr = E_FAIL;  
    OLECMD ocm={OLECMDID_PRINT, 0};  
 
    hr = m_lpObject->QueryInterface(IID_IOleCommandTarget,reinterpret_cast<void**>(&pCmd));

    if(FAILED(hr)) 
    return; 
 
    hr = pCmd->QueryStatus(NULL, 1, &ocm, NULL);

    if(SUCCEEDED(hr)&& (ocm.cmdf& OLECMDF_ENABLED))  
 { *//Command is available and enabled so call it  
    COleVariant vIn;  
    COleVariant vOut;  
    hr = pCmd->Exec(NULL, OLECMDID_PRINT,  
    OLECMDEXECOPT_DODEFAULT, &vIn, &vOut);

    ASSERT(SUCCEEDED(hr));

 }  
    pCmd->Release();

} 
```  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

