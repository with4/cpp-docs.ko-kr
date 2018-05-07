---
title: 'TN024: MFC에서 정의한 메시지 및 리소스 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC]
- Windows messages [MFC], MFC-defined
- messages [MFC], MFC
- TN024
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4dd403693dd860966cfcca42eacc909b01eb513b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tn024-mfc-defined-messages-and-resources"></a>TN024: MFC에서 정의한 메시지 및 리소스
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 내부 창 메시지 및 MFC에서 사용 되는 리소스 형식 설명 합니다. 이 정보는 프레임 워크의 구현에 설명 하 고 응용 프로그램을 디버깅 하는 데 도움이 됩니다. 형식에 대 한 이러한 모든 정보는 공식적으로 지원 되는 경우에 사용할 수 있습니다이 정보 중 일부 고급 구현에 대 한 합니다.  
  
 이 노트 포함 MFC private 구현 정보; 모든 내용을 나중에 변경 적용 됩니다. MFC 개인 Windows 메시지 한 응용 프로그램의 범위에서 의미가 있지만 시스템 전체 메시지를 포함 하는 나중에 변경 됩니다.  
  
 범위의 MFC 개인 Windows 메시지 및 리소스 종류는 예약 된 "시스템" 범위에 따로 Microsoft Windows에서 합니다. 현재 일부 숫자 범위에 사용 되 고, 나중에 새 범위에 사용할 수 있습니다. 현재 사용 되는 번호를 변경할 수 있습니다.  
  
 MFC 개인 Windows 메시지 0x360 범위에 있는 0x37F-> 합니다.  
  
 MFC 개인 리소스 유형 비트는 0xf0-0xFF > 합니다.  
  
 **MFC 개인 Windows 메시지**  
  
 이러한 Windows 메시지는 상대적으로 느슨하게 결합 되므로 필요한 경우 창 개체 소멸 시키기 사이 및 c + + 가상 함수를 적절 한 것입니다 c + + 가상 함수를 대신 사용 됩니다.  
  
 이러한 개인 Windows 메시지 및 관련된 매개 변수 구조는 MFC 개인 헤더에 선언 된 ' AFXPRIV 합니다. H'입니다. 이 헤더를 포함 하는 코드가 수 있습니다 수와에 의존 문서화 되지 않은 동작이 중단 될 이후 버전의 MFC 경고 합니다.  
  
 이러한 메시지 중 하나를 처리 하는 드문 경우를 사용할지는 `ON_MESSAGE` 메시지 맵 매크로 및 제네릭 LRESULT/WPARAM/LPARAM 형식으로 메시지를 처리 합니다.  
  
 **WM_QUERYAFXWNDPROC**  
  
 이 메시지는 생성 중인 창으로 전송 됩니다. WndProc 여부를 확인 하는 방법으로 보낸 생성 프로세스 초기에 **AfxWndProc 합니다. AfxWndProc** 1을 반환 합니다.  
  
|||  
|-|-|  
|wParam|사용되지 않음|  
|lParam|사용되지 않음|  
|returns|1에서 처리 하는 경우 **AfxWndProc**|  
  
 **WM_SIZEPARENT**  
  
 이 메시지 크기를 조정 하는 동안를 즉시 자식 프레임 창으로 전송 됩니다 (**CFrameWnd::OnSize** 호출 `CFrameWnd::RecalcLayout` 되는 호출 `CWnd::RepositionBars`) 주위 프레임의 면 컨트롤 막대의 위치를 변경 합니다. **AFX_SIZEPARENTPARAMS** 를 호출할 사용 하는 부모 / (NULL 일 수)는 HDWP 현재 사용 가능한 클라이언트 사각형을 포함 하는 구조 `DeferWindowPos` 다시 그리기를 최소화 하기 위해 합니다.  
  
|||  
|-|-|  
|wParam|사용되지 않음|  
|lParam|주소는 **AFX_SIZEPARENTPARAMS** 구조|  
|returns|사용 되지 않습니다 (0)|  
  
 메시지는 무시 나타냅니다 창 레이아웃에서 파트를 사용 하지 않습니다.  
  
 **WM_SETMESSAGESTRING**  
  
 상태 표시줄에서 메시지 줄을 업데이트 하도록 요청 하는 프레임 창에이 메시지가 보내집니다. 문자열 ID 또는 LPCSTR 지정 (하나만) 될 수 있습니다.  
  
|||  
|-|-|  
|wParam|문자열 ID (또는 0)|  
|lParam|문자열 (또는 NULL)에 대 한 LPCSTR|  
|returns|사용 되지 않습니다 (0)|  
  
 **WM_IDLEUPDATECMDUI**  
  
 이 메시지는 유휴 시간에 명령 업데이트 UI 처리기의 유휴 시간 업데이트를 구현 하 전송 됩니다. 만듭니다 (일반적으로 컨트롤 막대) 창에서 메시지를 처리 하는 경우는 `CCmdUI` 개체 (또는 파생된 클래스의 개체)를 호출 하 고 **CCmdUI::DoUpdate** 각 창에 "항목"에 대 한 합니다. 이 다시 확인에 대 한 프로그램 `ON_UPDATE_COMMAND_UI` 명령 처리기 체인에 있는 개체에 대 한 처리기입니다.  
  
|||  
|-|-|  
|wParam|BOOL bDisableIfNoHandler|  
|lParam|사용 되지 않습니다 (0)|  
|returns|사용 되지 않습니다 (0)|  
  
 *bDisableIfNoHandler* 0이 아니면 둘 다 UI 개체를 사용 하지 않도록 설정 하는 `ON_UPDATE_COMMAND_UI` 또는 `ON_COMMAND` 처리기입니다.  
  
 **WM_EXITHELPMODE**  
  
 이 메시지에 게시 되는 `CFrameWnd` 상황에 맞는 종료 하는 도움말 모드입니다. 이 메시지 수신에 의해 시작 모달 루프를 종료 **CFrameWnd::OnContextHelp 합니다.**  
  
|||  
|-|-|  
|wParam|사용 되지 않습니다 (0)|  
|lParam|사용 되지 않습니다 (0)|  
|returns|사용되지 않음|  
  
 **WM_INITIALUPDATE**  
  
 이 메시지 프레임 창의 모든 하위 항목의 초기 업데이트 작업 수에 대 한 안전할 경우 문서 템플릿에 의해 보내집니다. 에 대 한 호출에 매핑됩니다 `CView::OnInitialUpdate` 하지만 다른에 사용할 수 있는 `CWnd`-원 샷 다른 업데이트에 대 한 클래스를 파생 합니다.  
  
|||  
|-|-|  
|wParam|사용 되지 않습니다 (0)|  
|lParam|사용 되지 않습니다 (0)|  
|returns|사용 되지 않습니다 (0)|  
  
 **WM_RECALCPARENT**  
  
 이 메시지를 해당 부모 창 보기에서 전송 됩니다 (을 통해 얻은 `GetParent`)를 강제로 다시 계산 하는 레이아웃 (일반적으로 부모를 호출 합니다 `RecalcLayout`). OLE 서버 응용 프로그램에 프레임 보기의 총 크기까지 확장 되면서의 크기가 증가에 대 한 필요한 경우 사용 됩니다.  
  
 부모 창이이 메시지를 처리 하는 경우 TRUE를 반환 하 고 새 클라이언트 영역 크기와 lParam 전달 RECT 채우기입니다. 에 사용 됩니다 `CScrollView` 스크롤 막대 (다음 추가 될 때 창 외부에 위치)를 올바르게 처리 하려면 때 서버 개체는 내부 활성화.  
  
|||  
|-|-|  
|wParam|사용 되지 않습니다 (0)|  
|lParam|LPRECT rectClient NULL 일 수 있습니다.|  
|returns|TRUE 이면 새 클라이언트 사각형 반환, FALSE 그렇지 않은 경우|  
  
 **WM_SIZECHILD**  
  
 이 메시지를 보낼 `COleResizeBar` 소유자 창에 (통해 `GetOwner`) 사용자 크기 크기 조정 핸들을 사용 하 여 크기 조정 막대를 조정 합니다. `COleIPFrameWnd` 사용자가 요청한 대로 프레임 창 위치를 다시 시도 하 여이 메시지에 응답 합니다.  
  
 크기 조정 막대를 포함 하는 프레임 창 기준으로 클라이언트 좌표에 새 사각형 lParam에서 가리키고 있습니다.  
  
|||  
|-|-|  
|wParam|사용 되지 않습니다 (0)|  
|lParam|LPRECT rectNew|  
|returns|사용 되지 않습니다 (0)|  
  
 **WM_DISABLEMODAL**  
  
 이 메시지는은 비활성화 된 프레임 창이 소유한 모든 팝업 창으로 전송 됩니다. 프레임 창 결과 사용 하 여 팝업 창 사용 하지 않도록 설정할 것인지 여부를 결정 합니다.  
  
 프레임 모달 상태가 될 때 팝업 창에 특수 한 처리를 수행 하거나 특정 팝업 창을 가져오는 사용 하지 않도록 설정 하지 못하도록 하려면이 사용할 수 있습니다. 예를 들어 프레임 창을 모달 상태로 되 면 자체를 제거 하려면이 메시지를 사용 하는 도구 설명 합니다.  
  
|||  
|-|-|  
|wParam|사용 되지 않습니다 (0)|  
|lParam|사용 되지 않습니다 (0)|  
|returns|0이 아닌을 **하지** 는 창 사용 안 함, 0은 창을 사용할 수 없습니다|  
  
 **WM_FLOATSTATUS**  
  
 프레임 창 프레임 활성화 또는 비활성화 다른 최상위 프레임 창이 소유한 모든 팝업 창으로 전송 됩니다. 이 구현에 의해 사용 됩니다 **MFS_SYNCACTIVE** 에 `CMiniFrameWnd`를 팝업 창 활성화의 최상위 수준 프레임 창이 활성화 동기화 상태를 유지 합니다.  
  
|||  
|-|-|  
|wParam|다음 값 중 하나입니다.<br /><br /> **FS_SHOW**<br /><br /> **FS_HIDE**<br /><br /> **FS_ACTIVATE**<br /><br /> **FS_DEACTIVATE**<br /><br /> **FS_ENABLEFS_DISABLE**<br /><br /> **FS_SYNCACTIVE**|  
|lParam|사용 되지 않습니다 (0)|  
  
 반환 값 0이 아닌 값 이어야 합니다. 경우 **FS_SYNCACTIVE** 설정 되 고 창 동기화 부모 프레임을 사용 하 여 해당 활성화 합니다. `CMiniFrameWnd` 스타일으로 설정 된 경우 0이 아닌 반환 **MFS_SYNCACTIVE 합니다.**  
  
 자세한 내용은 참조 구현의 `CMiniFrameWnd`합니다.  
  
## <a name="wmactivatetoplevel"></a>WM_ACTIVATETOPLEVEL  
 이 메시지는 "최상위 그룹"에서 창을 활성화 또는 비활성화 하는 경우 최상위 창에 전송 됩니다. (없음 부모 또는 소유자)을 최상위 창 이거나 이러한 창을에서 소유 하 고 최상위 그룹의 일부는. 이 메시지를 사용 하 여에서 비슷합니다. **WM_ACTIVATEAPP,** 되지만 단일 창 계층 (OLE 응용 프로그램에서 일반적으로)에 서로 다른 프로세스에 속한 windows 혼합 되어 있는 경우에 작동 합니다.  
  
## <a name="wmcommandhelp-wmhelphittest-wmexithelpmode"></a>WM_COMMANDHELP, WM_HELPHITTEST, WM_EXITHELPMODE  
 이러한 메시지는 상황에 맞는 도움말의 구현에서 사용 됩니다. 참조 하십시오 [기술 참고 28](../mfc/tn028-context-sensitive-help-support.md) 자세한 정보에 대 한 합니다.  
  
## <a name="mfc-private-resource-formats"></a>MFC 개인 리소스 형식  
 MFC 두 개인 리소스 형식을 정의 하는 현재: **RT_TOOLBAR** 및 **RT_DLGINIT**합니다.  
  
## <a name="rttoolbar-resource-format"></a>RT_TOOLBAR 리소스 형식  
 응용 프로그램 마법사에서 제공 하는 기본 도구 모음 기반으로 한 **RT_TOOLBAR** MFC 4.0에서 도입 된 사용자 지정 리소스입니다. 도구 모음 편집기를 사용 하 여이 리소스를 편집할 수 있습니다.  
  
## <a name="rtdlginit-resource-format"></a>RT_DLGINIT 리소스 형식  
 추가 대화 상자 초기화 정보를 저장 한 MFC 개인 리소스 형식이 사용 됩니다. 콤보 상자에 저장 된 초기 문자열 포함 됩니다. 이 리소스의 형식은 수동으로 편집한 되도록 디자인 되지 않았지만 Visual c + +로 처리 합니다.  
  
 Visual c + + 및이 **RT_DLGINIT** 리소스 API 리소스의 정보를 사용 하지 않아도 되므로 MFC의 관련된 기능을 사용 하지 않아도 됩니다. Visual c + +를 사용 하면 훨씬 쉽게 작성, 관리 및 응용 프로그램을 장기적으로 변환할 수 있습니다.  
  
 기본 구조는 **RT_DLGINIT** 리소스는 다음과 같습니다.  
  
```  
+---------------+    \  
| Control ID    |   UINT             |  
+---------------+    |  
| Message #     |   UINT             |  
+---------------+    |  
|length of data |   DWORD            |  
+---------------+    |   Repeated  
|   Data        |   Variable Length  |   for each control  
|   ...         |   and Format       |   and message  
+---------------+    /  
|     0         |   BYTE  
+---------------+  
```  
  
 메시지를 보낼를 컨트롤 ID를 포함 하는 반복 되는 섹션 메시지 보내기 (표준 Windows 메시지) 및 데이터의 가변 길이 #. Windows 메시지 형태로 전송 됩니다.  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);
```  
  
 모든 Windows 메시지와 데이터 콘텐츠를 허용 하는 매우 일반적인 형식입니다. Visual c + + 리소스 편집기 및 MFC Windows 메시지의 제한 된 하위만 지원: CB_ADDSTRING 콤보 상자 (데이터는 텍스트 문자열)에 대 한 초기 목록을 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

