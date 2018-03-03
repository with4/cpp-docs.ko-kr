---
title: "CCommandLineInfo 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd5f24ccf18f39ef231f19aa5b837914104b57c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo 클래스
응용 프로그램을 시작할 때 명령줄을 구문 분석하는 데 유용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|기본 생성 `CCommandLineInfo` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CCommandLineInfo::ParseParam](#parseparam)|이 콜백은 개별 매개 변수를 구문 분석을 재정의 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|명령줄 나타냅니다 `/Automation` 옵션을 찾을 수 있습니다.|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|명령줄 나타냅니다 `/Embedding` 옵션을 찾을 수 있습니다.|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|시작 화면을 표시할지 여부를 나타냅니다.|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|셸 명령 처리를 나타냅니다.|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|드라이버를 나타내는 경우 셸 명령을 인쇄; 이름 그렇지 않은 경우 비어 있습니다.|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|열리거나 인쇄; 파일 이름을 나타냅니다. 빈 경우 신규 또는 DDE 셸 명령입니다.|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|포트를 나타내는 경우 셸 명령을 인쇄; 이름 그렇지 않은 경우 비어 있습니다.|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|프린터 나타냅니다 인쇄를; 셸 명령이 실행 되 면 이름 지정 그렇지 않은 경우 비어 있습니다.|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|다시 시작 관리자 응용 프로그램을 다시 시작 하는 경우 다시 시작 관리자에 대 한 다시 시작 고유 식별자를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 MFC 응용 프로그램에서이 클래스의 로컬 인스턴스에 만들어집니다 일반적으로 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 해당 응용 프로그램 개체의 기능입니다. 이 개체에 전달 되며 다음 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline), 반복적으로 호출 하는 [ParseParam](#parseparam) 채울는 `CCommandLineInfo` 개체입니다. `CCommandLineInfo` 에 전달 된 개체 다음 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand) 플래그 및 명령줄 인수를 처리 합니다.  
  
 다음 명령줄 옵션 및 매개 변수를 캡슐화 하이 개체를 사용할 수 있습니다.  
  
|명령줄 인수|실행 된 명령|  
|----------------------------|----------------------|  
|*app*|새 파일입니다.|  
|*응용 프로그램* 파일 이름|파일을 엽니다.|  
|*응용 프로그램* `/p` 파일 이름|파일을 기본 프린터로 인쇄 합니다.|  
|*응용 프로그램* `/pt` filename 프린터 드라이버 포트|파일을 지정된 된 프린터를 인쇄 합니다.|  
|*응용 프로그램*`/dde`|시작 하 고 DDE 명령의 기다립니다.|  
|*응용 프로그램*`/Automation`|OLE 자동화 서버를 시작 합니다.|  
|*응용 프로그램*`/Embedding`|포함된 된 OLE 항목 편집을 시작 합니다.|  
|*응용 프로그램*`/Register`<br /><br /> *응용 프로그램*`/Regserver`|등록 작업 수행 하기 위해 응용 프로그램을 알립니다.|  
|*응용 프로그램*`/Unregister`<br /><br /> *응용 프로그램*`/Unregserver`|등록 취소 작업 수행 하기 위해 응용 프로그램을 알립니다.|  
  
 새 클래스를 파생 `CCommandLineInfo` 다른 플래그와 매개 변수 값을 처리할 수 있습니다. 재정의 [ParseParam](#parseparam) 새 플래그를 처리할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo  
 이 생성자는 `CCommandLineInfo` 기본값을 사용 하는 개체입니다.  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>설명  
 기본값은 시작 화면 표시를 ( `m_bShowSplash=TRUE`) 파일 메뉴에서 새로 만들기 명령을 실행할 수 ( `m_nShellCommand` **NewFile =**).  
  
 응용 프로그램 프레임 워크 호출 [ParseParam](#parseparam) 을이 개체의 데이터 멤버를 채웁니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated  
 나타냅니다는 `/Automation` 명령줄에서 플래그를 찾았습니다.  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>설명  
 경우 `TRUE`, 즉, OLE 자동화 서버 시작 합니다.  
  
##  <a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded  
 나타냅니다는 `/Embedding` 명령줄에서 플래그를 찾았습니다.  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>설명  
 경우 `TRUE`, 즉, 포함된 된 OLE 항목 편집을 시작 합니다.  
  
##  <a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash  
 시작 화면을 표시 해야 함을 나타냅니다.  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>설명  
 경우 `TRUE`, 즉, 시작 화면 시작 하는 동안이 응용 프로그램을 표시 해야 합니다. 기본 구현은 [ParseParam](#parseparam) 이 데이터 멤버 설정 하는 `TRUE` 경우 [m_nShellCommand](#m_nshellcommand) 같으면 `CCommandLineInfo::FileNew`합니다.  
  
##  <a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand  
 응용 프로그램의이 인스턴스에 대 한 셸 명령을 나타냅니다.  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>설명  
 이 데이터 멤버에 대 한 형식은 다음과 같은 열거 형식에 정의 된는 `CCommandLineInfo` 클래스입니다.  
  
```  
enum {  
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1  
    };  
```  
  
 에 대 한 간략 한 설명은 다음이 값을 다음 목록을 참조 합니다.  
  
- `CCommandLineInfo::FileNew`파일 이름을 명령줄에서 찾지 못했습니다. 나타냅니다.  
  
- `CCommandLineInfo::FileOpen`명령줄에서 파일 이름을 찾을 수 있는지와 명령줄에서이 찾지 못한 다음 플래그를 나타냅니다: `/p`, `/pt`, `/dde`합니다.  
  
- `CCommandLineInfo::FilePrint`나타냅니다는 `/p` 명령줄에서 플래그를 찾았습니다.  
  
- `CCommandLineInfo::FilePrintTo`나타냅니다는 `/pt` 명령줄에서 플래그를 찾았습니다.  
  
- `CCommandLineInfo::FileDDE`나타냅니다는 `/dde` 명령줄에서 플래그를 찾았습니다.  
  
- `CCommandLineInfo::AppRegister`나타냅니다는 `/Register` 또는 `/Regserver` 플래그를 명령줄에서 찾을 수 및 응용 프로그램을 등록 하 라는 요청입니다.  
  
- `CCommandLineInfo::AppUnregister`나타냅니다는 `/Unregister` 또는 `/Unregserver` 응용 프로그램의 등록을 취소 하 라는 요청입니다.  
  
- `CCommandLineInfo::RestartByRestartManager`되는 응용 프로그램 다시 시작 관리자가 다시 시작 되었음을 나타냅니다.  
  
- `CCommandLineInfo::FileNothing`시작할 때 새 MDI 자식 창이 표시 되지 않습니다. 기본적으로 응용 프로그램 마법사에서 생성 된 MDI 응용 프로그램 시작 시 새 자식 창을 표시. 이 기능을 해제 하려면 응용 프로그램 사용 `CCommandLineInfo::FileNothing` 셸 명령을 호출할 때 [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)합니다. `ProcessShellCommand`에 의해 호출 됩니다는 `InitInstance( )` 모든 `CWinApp` 파생 클래스입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName  
 명령줄에서 세 번째 비 플래그 매개 변수의 값을 저장합니다.  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>설명  
 이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터 드라이버의 이름입니다. 기본 구현은 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 명령줄에서 플래그를 찾았습니다.  
  
##  <a name="m_strfilename"></a>CCommandLineInfo::m_strFileName  
 명령줄에서 첫 번째 비 플래그 매개 변수의 값을 저장합니다.  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>설명  
 이 매개 변수는 일반적으로 열 파일의 이름입니다.  
  
##  <a name="m_strportname"></a>CCommandLineInfo::m_strPortName  
 명령줄에서 네 번째 비 플래그 매개 변수 값을 저장합니다.  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>설명  
 이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터 포트의 이름입니다. 기본 구현은 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 명령줄에서 플래그를 찾았습니다.  
  
##  <a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName  
 명령줄에서 두 번째 비 플래그 매개 변수 값을 저장합니다.  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>설명  
 이 매개 변수는 일반적으로 인쇄에 셸 명령에 대 한 프린터의 이름입니다. 기본 구현은 [ParseParam](#parseparam) 설정 하는 경우에만이 데이터 멤버는 `/pt` 명령줄에서 플래그를 찾았습니다.  
  
##  <a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier  
 고유 식별자는 명령줄에서를 다시 시작합니다.  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>설명  
 다시 시작 식별자는 응용 프로그램의 각 인스턴스에 대해 고유 합니다.  
  
 다시 시작 관리자는 응용 프로그램을 종료 하 고 다시 시작 하도록 구성 된, 다시 시작 관리자 실행 응용 프로그램 다시 시작 식별자를 사용 하 여 명령줄에서 선택적 매개 변수로 사용 합니다. 다시 시작 관리자를 다시 시작 식별자가 사용 될 경우 응용 프로그램 이전에 열려 있는 문서를 다시 열를 업데이트 하 고 자동 저장 된 파일을 복구할 수 있습니다.  
  
##  <a name="parseparam"></a>CCommandLineInfo::ParseParam  
 프레임 워크 명령줄에서 개별 매개 변수를 구문 분석/해석 하려면이 함수를 호출 합니다. 두 번째 버전은 첫 번째에서 다른 유니코드 프로젝트에만 합니다.  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszParam`  
 매개 변수 또는 플래그입니다.  
  
 *bFlag*  
 나타냅니다 여부 `pszParam` 는 매개 변수 인지 또는 플래그입니다.  
  
 `bLast`  
 이 마지막 매개 변수 또는 명령줄에서 플래그는 경우를 나타냅니다.  
  
### <a name="remarks"></a>설명  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline) 호출 `ParseParam` 한 번 각 매개 변수 또는 명령줄에서 플래그에 대 한 인수를 전달 `pszParam`합니다. 매개 변수의 첫 번째 문자는 경우는 '  **-** '또는'  **/** ', 없어지기 다음 및 *bFlag* 로 설정 된 `TRUE`합니다. 마지막 매개 변수를 구문 분석할 때 `bLast` 로 설정 된 `TRUE`합니다.  
  
 이 함수의 기본 구현은 다음과 같은 플래그 인식: `/p`, `/pt`, `/dde`, `/Automation`, 및 `/Embedding`다음 표에 표시 된 것 처럼:  
  
|명령줄 인수|실행 된 명령|  
|----------------------------|----------------------|  
|*app*|새 파일입니다.|  
|*응용 프로그램* 파일 이름|파일을 엽니다.|  
|*응용 프로그램* `/p` 파일 이름|파일을 기본 프린터로 인쇄 합니다.|  
|*응용 프로그램* `/pt` filename 프린터 드라이버 포트|파일을 지정된 된 프린터를 인쇄 합니다.|  
|*응용 프로그램*`/dde`|시작 하 고 DDE 명령의 기다립니다.|  
|*응용 프로그램*`/Automation`|OLE 자동화 서버를 시작 합니다.|  
|*응용 프로그램*`/Embedding`|포함된 된 OLE 항목 편집을 시작 합니다.|  
|*응용 프로그램*`/Register`<br /><br /> *응용 프로그램*`/Regserver`|등록 작업 수행 하기 위해 응용 프로그램을 알립니다.|  
|*응용 프로그램*`/Unregister`<br /><br /> *응용 프로그램*`/Unregserver`|등록 취소 작업 수행 하기 위해 응용 프로그램을 알립니다.|  
  
 이 정보에 저장 됩니다 [m_bRunAutomated](#m_brunautomated), [m_bRunEmbedded](#m_brunembedded), 및 [m_nShellCommand](#m_nshellcommand)합니다. 플래그는 슬래시로 표시 된 '  **/** '또는 하이픈'  **-** '.  
  
 기본 구현에 첫 번째 비 플래그 매개 변수를 배치 [m_strFileName](#m_strfilename)합니다. 경우에 `/pt` 플래그를 기본 구현은 배치 두 번째, 세 번째 및 네 번째 비 플래그 매개 변수를 [m_strPrinterName](#m_strprintername), [m_strDriverName](#m_strdrivername), 및 [m_ strPortName](#m_strportname)각각.  
  
 기본 구현은 설정 [m_bShowSplash](#m_bshowsplash) 를 `TRUE` 새 파일의 경우에 합니다. 새 파일의 경우 사용자는 응용 프로그램 자체와 관련 된 작업을 수행 했습니다. 다른 모든 경우는 셸을 사용 하 여 기존 파일을 열을 포함 하 여 사용자 작업은 파일 포함 직접 됩니다. 문서 중심의 관점에서 시작 화면이 응용 프로그램 시작을 발표 하 게 필요 하지 않습니다.  
  
 다른 플래그와 매개 변수 값을 처리 하려면 파생된 클래스에서이 함수를 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

