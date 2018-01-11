---
title: "TN028: 상황에 맞는 도움말 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.help
dev_langs: C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8054fe4fae4aafa88c34833a5a2a92a6b9b44bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: 상황에 맞는 도움말 지원
이 노트 도움말 컨텍스트 Id와 MFC에서 기타 도움말 문제를 지정 하는 것에 대 한 규칙을 설명 합니다. 상황에 맞는 도움말 지원에는 Visual c + +에서 사용할 수 있는 도움말 컴파일러가 필요 합니다.  
  
> [!NOTE]
>  WinHelp를 사용 하 여 상황에 맞는 도움말에 뿐만 아니라 MFC HTML 도움말 사용도 지원 합니다. 이 지원 및 HTML 도움말을 사용 하 여 프로그래밍에 대 한 자세한 내용은 참조 하십시오. [HTML 도움말: 프로그램에 대 한 상황에 맞는 도움말](../mfc/html-help-context-sensitive-help-for-your-programs.md)합니다.  
  
## <a name="types-of-help-supported"></a>도움말 지원  
 Windows 응용 프로그램에서 구현 되는 상황에 맞는 도움말에는 다음과 같은 두 종류가 있습니다. 현재 활성 상태인 개체에 따라 적절 한 컨텍스트에 WinHelp 시작 포함 "F1 Help"를 첫 번째 라고 합니다. 두 번째는 "Shift + F1" 모드입니다. 이 모드에서 마우스 커서가 도움말 커서를 변경 하 고 사용자 개체를 클릭 하 여 진행 됩니다. 해당 시점에 사용자를 클릭 하는 개체에 대 한 도움말을 제공할 WinHelp 시작 됩니다.  
  
 Microsoft Foundation Classes 도움말의 다음이 형식 중 둘 다 구현 합니다. 또한 프레임 워크 도움말 색인 및 도움말 사용 하 여 두 개의 간단한 도움말 명령을 지원 합니다.  
  
## <a name="help-files"></a>도움말 파일  
 Microsoft Foundation 클래스는 단일 도움말 파일을 가정합니다. 해당 도움말 파일에는 응용 프로그램과 동일한 이름 및 경로 있어야 합니다. 예를 들어 실행 파일이 C:\MyApplication\MyHelp.exe 인 경우에 도움말 파일 C:\MyApplication\MyHelp.hlp 이어야 합니다. 경로 통해 설정한는 `m_pszHelpFilePath` 의 멤버 변수는 [CWinApp 클래스](../mfc/reference/cwinapp-class.md)합니다.  
  
## <a name="help-context-ranges"></a>도움말 컨텍스트 범위  
 MFC의 기본 구현은 도움말 컨텍스트 Id의 할당에 대 한 몇 가지 규칙을 따르도록 프로그램이 필요 합니다. 이러한 규칙은 특정 컨트롤에 할당 된 Id 범위입니다. 다양 한 멤버 도움말 관련 함수의 다른 구현을 제공 하 여 이러한 규칙을 재정의할 수 있습니다.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
0x00020000 + IDR_  
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
0x00040000 + IDW_  
```  
  
## <a name="simple-help-commands"></a>간단한 "도움말" 명령  
 Microsoft Foundation 클래스에서 구현 되는 두 개의 간단한 도움말 명령입니다.  
  
-   구현 하는 ID_HELP_INDEX [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   구현 하는 ID_HELP_USING [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 첫 번째 명령은 응용 프로그램에 대 한 도움말 색인을 보여 줍니다. 두 번째 WinHelp 프로그램을 사용 하 여에 사용자 도움말을 표시 합니다.  
  
## <a name="context-sensitive-help-f1-help"></a>상황에 맞는 도움말 (F1 도움말)  
 F1 키의 ID 사용 하는 명령은 일반적으로 변환 됩니다 `ID_HELP` 주 창의 액셀러레이터 키 테이블에 배치 하는 가속기가 있습니다. `ID_HELP` 명령 ID로는 단추를 통해 생성 될 수도 있습니다 `ID_HELP` 주 창 또는 대화 상자에 있습니다.  
  
 방식과 관계 없이 `ID_HELP` 명령이 생성, 명령 처리기에 도달할 때까지 일반적인 명령으로 라우팅됩니다. MFC 명령 라우팅 아키텍처에 대 한 자세한 내용은를 참조 [기술 참고 21](../mfc/tn021-command-and-message-routing.md)합니다. 응용 프로그램에 도움말을 사용 하는 경우는 `ID_HELP` 명령에서 처리 되는 [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp)합니다. Application 개체 도움말 메시지를 받고 한 후 명령의 적절 하 게 라우팅합니다. 가장 구체적인 컨텍스트 확인에 적합 하지 않은 기본 명령 라우팅 있으므로이 과정이 필요 합니다.  
  
 `CWinApp::OnHelp`다음과 같은 순서로 WinHelp를 시작 하려고 합니다.  
  
1.  활성 검사 `AfxMessageBox` 호출는 도움말 id. 메시지 상자가 현재 활성 상태 이면 WinHelp 해당 messagebox에 적절 한 상황에 맞는으로 시작 됩니다.  
  
2.  활성 창으로 WM_COMMANDHELP 메시지를 보냅니다. WinHelp를 시작 하 여 응답 하지 않으면 해당 창 메시지를 처리할 때까지 현재 최상위 창입니다 같은 메시지는 다음 해당 창의 상위 항목에 전송 됩니다.  
  
3.  ID_DEFAULT_HELP 명령을 주 창에 보냅니다. 기본 도움말을 호출합니다. 이 명령은에 일반적으로 매핑된 `CWinApp::OnHelpIndex`합니다.  
  
 응용 프로그램 전역 기본 ID 기준 값 (예: 명령에 대 한 0x10000 및 대화 상자와 같은 리소스에 대 한 0x20000)을 재정의 하려면 재정의 해야 [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp)합니다.  
  
 도움말 컨텍스트 결정 되는 방법과이 기능을 재정의 하려면 WM_COMMANDHELP 메시지를 처리 해야 합니다. 보다 구체적인 도움말 라우팅을 제공 프레임 워크가 제공 하는 것만 되는 것 만큼 현재 MDI 자식 창으로 심층 할 수 있습니다. 특정 창 또는 대화 상자에서 해당 개체 또는 대화 상자 내에서 활성 컨트롤의 현재 내부 상태 기반에 대 한 자세한 도움말을 제공 수도 있습니다.  
  
## <a name="wmcommandhelp"></a>WM_COMMANDHELP  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 WM_COMMANDHELP는 도움말을 요청할 때 활성 창에서 수신 하는 개인 Windows MFC 메시지입니다. 창에서이 메시지를 받으면 호출할 수 있습니다 `CWinApp::WinHelp` 창 내부 상태와 일치 하는 컨텍스트를 사용 합니다.  
  
 `lParam`  
 현재 사용할 수 있는 도움말 컨텍스트를 포함 합니다. `lParam`도움말 컨텍스트가 없는 확인 된 경우에 0입니다. 구현 `OnCommandHelp` 에 컨텍스트 ID를 사용할 수 `lParam` 에 다른 컨텍스트를 결정 하거나 전달 방금 수 `CWinApp::WinHelp`합니다.  
  
 `wParam`  
 사용 되지 않으며 0이 됩니다.  
  
 경우는 `OnCommandHelp` 함수 호출 `CWinApp::WinHelp`를 반환 해야 `TRUE`합니다. 반환 `TRUE` 다른 클래스에 다른 창에이 명령의 라우팅이 중지 합니다.  
  
## <a name="help-mode-shiftf1-help"></a>도움말 모드 (Shift + F1 도움말)  
 이 두 번째 형태 상황에 맞는 도움말입니다. 일반적으로이 모드는 SHIFT + F1 키를 눌러 또는 메뉴/도구 모음을 통해 입력 합니다. 명령으로 구현 됩니다 (**ID_CONTEXT_HELP**). 메시지 필터 후크 모달 대화 상자는 동안이 명령은 변환에 사용 되지 않는 또는 메뉴가 활성화 된 경우이 명령은 이므로 사용자에 게 사용할 수 있는 경우 기본 메시지 펌프를 실행 하는 응용 프로그램 (`CWinApp::Run`).  
  
 이 모드를 입력 한 후 응용 프로그램은 일반적으로 해당 영역 (예: 창 주변의 크기 조정 테두리)에 대 한 자체 커서를 표시 하는 경우에 도움말 마우스 커서는 응용 프로그램의 모든 영역을 통해 표시 됩니다. 사용자는 마우스나 키보드를 사용 하 여 명령을 선택할 수 있습니다. 이 명령은 실행 하는 대신 해당 명령에 대 한 도움말 표시 됩니다. 또한 사용자는 도구 모음의 단추와 같은 화면에 표시 되는 개체를 클릭할 수 및 해당 개체에 대 한 도움말을 표시 됩니다. 도움말의이 모드에서 제공 `CWinApp::OnContextHelp`합니다.  
  
 이 루프의 실행 하는 동안 모든 키보드 입력 메뉴에 액세스 하는 키를 제외 하 고 활성 상태가 아닙니다. 또한 명령 변환에도 수행 통해 `PreTranslateMessage` 사용자 액셀러레이터 키를 누르고 해당 명령에 도움을 받을 수 있도록 합니다.  
  
 번역 또는 동작 수행에 배치할 경우 특정는 `PreTranslateMessage` 안 도중 발생 하는 SHIFT + F1 도움말 모드를 확인 해야 함수는 `m_bHelpMode` 소속 `CWinApp` 이러한 작업을 수행 하기 전에. `CDialog` 구현의 `PreTranslateMessage` 호출 하기 전에이 확인 `IsDialogMessage`, 예를 들어 있습니다. 그러면 SHIFT + f 1 모드에 있는 동안 모덜리스 대화 상자에 "대화 탐색" 키를 해제합니다. 또한 `CWinApp::OnIdle` 는이 루프 중 호출 됩니다.  
  
 해당 명령에 대 한 도움말으로 처리 되는 메뉴에서 명령의 선택 하는 경우 (통해 **WM_COMMANDHELP**, 아래 참조). 사용자가 응용 프로그램 창의 표시 영역을 클릭 하면 사용할지 여부를 결정 한 비클라이언트 또는 클라이언트 클릭 결정이 이루어집니다. `OnContextHelp`비클라이언트의 핸들 매핑을 자동으로 클라이언트 클릭에 클릭합니다. 그런 다음 보냅니다 클라이언트 클릭 인 경우는 **WM_HELPHITTEST** 클릭 된 창에 있습니다. 해당 창에서 0이 아닌 값을 반환 하는 경우 해당 값에 대 한 도움말 컨텍스트도 사용 됩니다. 0을 반환 하는 경우 `OnContextHelp` 시도 부모 창 (및 해당 스레드가 없으면 해당 부모와 같이). 기본값은 보낼 도움말 컨텍스트를 확인할 수 없는 경우는 **ID_DEFAULT_HELP** 명령을에 매핑되는 다음 일반적으로 주 창에 `CWinApp::OnHelpIndex`합니다.  
  
## <a name="wmhelphittest"></a>WM_HELPHITTEST  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 **WM_HELPHITTEST** SHIFT + F1 도움말 모드에 있는 동안 클릭 하면 활성 창에서 수신 되는 MFC 개인 windows 메시지입니다. 창에서이 메시지를 받으면 WinHelp에서 사용 하기 위해 DWORD 도움말 ID를 반환 합니다.  
  
 LOWORD(lParam)  
 창의 클라이언트 영역을 기준으로 마우스를 클릭 하는 x 축 장치 좌표가 포함 됩니다.  
  
 HIWORD(lParam)  
 y 축 좌표를 포함합니다.  
  
 `wParam`  
 사용 되지 않으며 0이 됩니다. 반환 값이 0이 아닌 경우 해당 컨텍스트와 함께 WinHelp 라고 합니다. 반환 값이 0 인 경우 부모 창에 대 한 도움말 쿼리 됩니다.  
  
 대부분의 경우에서 이미 있을 수는 적중 테스트 코드를 활용할 수 있습니다. 구현을 참조 **CToolBar::OnHelpHitTest** 처리에 대 한 예제는 **WM_HELPHITTEST** 메시지 (코드에서 단추 및 도구 설명에 사용 되는 적중 테스트 코드를 활용 하 여 `CControlBar`).  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>MFC 응용 프로그램 마법사 지원 및 MAKEHM  
 MFC 응용 프로그램 마법사 도움말 파일 (.cnt 및.hpj 파일)을 작성 하는 데 필요한 파일을 만듭니다. Microsoft 도움말 컴파일러에서 허용 되는 미리 작성 된.rtf 파일 수가 포함 됩니다. 대부분의 항목은이 완료 되 면 하지만 특정 응용 프로그램에 맞게 수정 해야 할 수 있습니다.  
  
 "매핑 도움말" 파일의 자동 만들기 MAKEHM 라는 유틸리티에서 지원 됩니다. MAKEHM 유틸리티 응용 프로그램의 리소스를 변환할 수 있습니다. H 파일 도움말 매핑 파일입니다. 예:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 로 변환 됩니다.  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 이 형식은 (왼쪽에 있는 기호) 항목 이름의 컨텍스트 Id (오른쪽에 숫자)를 매핑하는 도움말 컴파일러의 기능과 호환 됩니다.  
  
 MAKEHM에 대 한 소스 코드는 MFC 프로그래밍 유틸리티 예제에서 사용할 수 있는 [MAKEHM](../visual-cpp-samples.md)합니다.  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC 응용 프로그램 마법사를 실행 한 후 도움말 지원 추가  
 도움말 응용 프로그램을 추가 하는 가장 좋은 방법은 응용 프로그램을 만들기 전에 MFC 응용 프로그램 마법사의 고급 기능 페이지에서 "상황에 맞는 도움말" 옵션 것뿐입니다. 이런 방식으로 MFC 응용 프로그램 마법사에 필요한 메시지 맵 항목 자동으로 추가 하면 `CWinApp`-도움말을 지원 하기 위해 클래스를 파생 합니다.  
  
## <a name="help-on-message-boxes"></a>메시지 상자에 대 한 도움말  
 메시지 상자 (경고)에 대 한 도움말을 통해 사용할 수는 `AfxMessageBox` 함수에 대 한 래퍼는 `MessageBox` Windows API입니다.  
  
 두 가지 버전의 `AfxMessageBox`, 다른 하나는 문자열 ID와 문자열에 대 한 포인터와 함께 사용할 (`LPCSTR`):  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 두 경우 모두, 즉는 선택적 도움말 id입니다.  
  
 첫 번째 경우 nIDHelp에 대 한 기본값은 0 이며이 메시지 상자에 대 한 도움말을 의미 합니다. 예: 메시지 상자는 활성화 하는 동안 f1 키를 누를, 사용자 (경우에 응용 프로그램이 도움말 지원) 도움말을 받지 못합니다. 필요 없는 경우 nIDHelp에 대 한 도움말 ID는 제공 합니다.  
  
 두 번째 경우에는 기본 nIDHelp 점은 도움말 ID nIDPrompt 같습니다 나타내는-1입니다. 도움말 응용 프로그램은 도움말 사용의 다양 한 경우에 작동 합니다). 메시지 상자는 도움말 지원 되지 원하면 nIDHelp에 대 한 0을 제공 해야 합니다. 사용 하도록 설정 하는 도움말 하지만 nIDPrompt 보다 다른 도움말 ID를 원하는 nIDHelp nIDPrompt의에 대 한 양수 값을 제공 하기만 하면 메시지를 받으려면 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

