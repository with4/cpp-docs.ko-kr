---
title: CUserTool 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
dev_langs:
- C++
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59f5ab622d6124e830028ea61a0c77583f76d015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374755"
---
# <a name="cusertool-class"></a>CUserTool 클래스
사용자 도구는 외부 응용 프로그램을 실행하는 메뉴 항목입니다. **도구** 탭은 **사용자 지정** 대화 상자 ( [CMFCToolBarsCustomizeDialog 클래스](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) 사용 하면 사용자 도구를 추가 하 고 이름, 명령, 인수를 지정 하 고 각 사용자 도구에 대 한 초기 디렉터리입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|지정된 된 사각형에 사용자 도구 아이콘을 그립니다.|  
|[CUserTool::GetCommand](#getcommand)|사용자 도구와 관련 된 명령의 텍스트를 포함 하는 문자열을 반환 합니다.|  
|[CUserTool::GetCommandId](#getcommandid)|사용자 도구 메뉴 항목의 명령 ID를 반환합니다.|  
|[CUserTool::Invoke](#invoke)|사용자 도구와 관련 된 명령을 실행 합니다.|  
|[CUserTool::Serialize](#serialize)|이 개체를 보관 저장소에서 읽어오거나 보관 저장소에 씁니다. ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)를 재정의합니다.)|  
|[CUserTool::SetCommand](#setcommand)|사용자 도구와 관련 된 명령을 설정 합니다.|  
|[CUserTool::SetToolIcon](#settoolicon)|이 도구와 연결 된 응용 프로그램에서 사용자 도구에 대 한 아이콘을 로드 합니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|사용자 도구에 대 한 기본 아이콘을 로드합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|사용자 도구에 대 한 명령줄 인수입니다.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|사용자 도구에 대 한 초기 디렉터리입니다.|  
|[CUserTool::m_strLabel](#m_strlabel)|이 도구에 대 한 메뉴 항목에 표시 되는 도구 이름입니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에서 사용자 도구를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 참조 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 도구를 만드는 방법을 보여 줍니다는 `CUserToolsManager` 개체, 설정 된 `m_strLabel` 멤버 변수와 사용자 도구를 실행 하는 응용 프로그램 집합입니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon  
 지정된 된 사각형의 가운데에 사용자 도구 아이콘을 그립니다.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pDC`  
 장치 컨텍스트에 대한 포인터입니다.  
  
 [in] `rectImage`  
 아이콘을 표시 하는 영역의 좌표를 지정 합니다.  
  
##  <a name="getcommand"></a>  CUserTool::GetCommand  
 사용자 도구와 관련 된 명령의 텍스트를 포함 하는 문자열을 반환 합니다.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조 `CString` 사용자 도구와 연결 된 명령 텍스트를 포함 하는 개체입니다.  
  
##  <a name="getcommandid"></a>  CUserTool::GetCommandId  
 사용자 도구의 명령 ID를 반환합니다.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 사용자 도구 명령 ID입니다.  
  
##  <a name="invoke"></a>  CUserTool::Invoke  
 사용자 도구와 관련 된 명령을 실행 합니다.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>반환 값  
 명령이 성공적으로 실행 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) 사용자 도구와 관련 된 명령을 실행할 수 있습니다. 이 명령은 비어 있거나 경우 함수가 실패 하면 [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) 실패 합니다.  
  
##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon  
 사용자 도구에 대 한 기본 아이콘을 로드합니다.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>반환 값  
 로드 된 아이콘에 대 한 핸들 ( `HICON`), 또는 `NULL` 기본 아이콘을 로드할 수 없는 경우.  
  
### <a name="remarks"></a>설명  
 프레임 워크 도구 실행 파일에서 사용자 정의 도구에 대 한 아이콘을 로드할 수 없는 경우이 메서드를 호출 합니다.  
  
 사용자 고유의 기본 도구 아이콘을 제공 하려면이 메서드를 재정의 합니다.  
  
##  <a name="m_strarguments"></a>  CUserTool::m_strArguments  
 사용자 도구에 대 한 명령줄 인수입니다.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>설명  
 이 문자열은 호출 하는 경우이 도구에 전달 [CUserTool::Invoke](#invoke) 또는 클릭 한 경우이 도구와 연결 된 명령입니다.  
  
##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory  
 사용자 도구에 대 한 초기 디렉터리를 지정합니다.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>설명  
 이 변수를 호출할 때에 실행 되는 도구는 초기 디렉터리를 지정 [CUserTool::Invoke](#invoke) 또는 클릭 한 경우이 도구와 연결 된 명령입니다.  
  
##  <a name="m_strlabel"></a>  CUserTool::m_strLabel  
 이 도구에 대 한 메뉴 항목에 표시 되는 레이블.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>  CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `ar`  
  
### <a name="remarks"></a>설명  
  
##  <a name="setcommand"></a>  CUserTool::SetCommand  
 사용자 도구를 실행 하는 응용 프로그램을 설정 합니다.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszCmd`  
 사용자 도구와 연결할 새 응용 프로그램을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 사용자 도구를 실행 하는 새 응용 프로그램을 설정 하려면이 메서드를 호출 합니다. 메서드는 이전 아이콘을 제거 하 고 특정된 응용 프로그램에서 새 아이콘을 로드 합니다. 응용 프로그램에서 아이콘을 로드할 수 없습니다 것을 하면 로드를 호출 하 여 사용자 도구에 대 한 기본 아이콘 [CUserTool::LoadDefaultIcon](#loaddefaulticon)합니다.  
  
##  <a name="settoolicon"></a>  CUserTool::SetToolIcon  
 이 도구를 사용 하는 응용 프로그램에서 사용자 도구에 대 한 아이콘을 로드 합니다.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>반환 값  
 로드 된 아이콘에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 메뉴 항목에 표시할 아이콘을 로드 하려면이 메서드를 호출 합니다. 이 메서드는이 도구를 사용 하는 실행 파일에 있는 아이콘에 대 한 검색 합니다. 아이콘에서 제공 하는 기본 아이콘 없기 경우 [CUserTool::LoadDefaultIcon](#loaddefaulticon) 대신 사용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager 클래스](../../mfc/reference/cusertoolsmanager-class.md)
