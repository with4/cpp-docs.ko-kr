---
title: CBitmapButton 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ba2a3f54ff39341c43ee497fcccda43cd3625fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358357"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton 클래스
텍스트가 아닌 비트맵 이미지로 레이블이 표시된 누름 단추 컨트롤을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|`CBitmapButton` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|대화 상자에서 단추의 개체와 연결 된 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 비트맵에 맞게 단추 크기를 조정 합니다.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|응용 프로그램의 리소스 파일에서 하나 이상의 명명 된 비트맵 리소스를 로드 하는 비트맵 개체에 연결 하 여 개체를 초기화 합니다.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|비트맵에 맞게 단추 크기를 조정 합니다.|  
  
## <a name="remarks"></a>설명  
 `CBitmapButton` 개체 단추 간주 될 수 있는 여러 상태에 대 한 이미지를 포함 하는 최대 4 개의 비트맵에 포함: 위쪽 (또는 일반) 아래쪽 (또는 선택한) 치중 하 고 사용 하지 않도록 설정 합니다. 첫 번째 비트맵에만 필수 사항입니다. 나머지는 선택 사항입니다.  
  
 비트맵 단추 이미지의 테두리는 이미지 뿐만 아니라 이미지 자체 포함 됩니다. 테두리는 일반적으로 한 역할 단추의 상태를 표시 합니다. 예를 들어 포커스가 있는 상태에 대 한 비트맵은 일반적으로 같은 테두리 또는 테두리에 굵은 실선에서 파선된 사각형 inset 하면서도 최신 상태에 대 한 하나입니다. 비트맵의 disabled 일반적으로 상태에 대 한 유사 한 놓여 않았으나 낮은 대비 (예: 회색 또는 흐리게 메뉴 선택)에 대 한 합니다.  
  
 이러한 비트맵의 크기나 수는 있지만 큐브인 것 처럼 동일한 크기의 최신 상태에 대 한 비트맵 모두 처리 됩니다.  
  
 비트맵 이미지의 다양 한 조합을 요구 하는 다양 한 응용 프로그램:  
  
|위로|아래로|포커스 있음|사용 안 함|응용 프로그램|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||단추 없이 **WS_TABSTOP** 스타일|  
|×|×|×|×|모든 상태와 대화 상자 단추|  
|×|×|×||대화 상자 단추와 **WS_TABSTOP** 스타일|  
  
 비트맵 단추 컨트롤을 만들 때 설정 된 **BS_OWNERDRAW** 소유자가 그린 단추 인지를 지정 하는 스타일입니다. 이 인해를 보냅니다는 `WM_MEASUREITEM` 및 `WM_DRAWITEM` 단추에 대 한 메시지 프레임 워크 이러한 메시지를 처리 하 고 드립니다 단추의 모양을 관리 합니다.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>창의 클라이언트 영역에서 비트맵 단추 컨트롤을 만들려면  
  
1.  단추에 대해 1 ~ 4 개의 비트맵 이미지를 만듭니다.  
  
2.  생성 된 [CBitmapButton](#cbitmapbutton) 개체입니다.  
  
3.  호출 된 [만들기](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고에 연결 하는 함수는 `CBitmapButton` 개체입니다.  
  
4.  호출 된 [LoadBitmaps](#loadbitmaps) 비트맵 단추를 생성 한 후 비트맵 리소스를 로드 하는 멤버 함수입니다.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>대화 상자에는 비트맵 단추 컨트롤을 포함 하려면  
  
1.  단추에 대해 1 ~ 4 개의 비트맵 이미지를 만듭니다.  
  
2.  비트맵 단추 원하는 위치로 옮깁니다 소유자 그리기 단추가 있는 대화 상자 템플릿을 만듭니다. 서식 파일에 있는 단추의 크기 중요 하지 않습니다.  
  
3.  와 같은 값으로 단추의 캡션을 설정 " **MYIMAGE**"와 같은 단추에 대 한 기호를 정의 하 고 **IDC_MYIMAGE**합니다.  
  
4.  응용 프로그램의 리소스 스크립트에 각 문자 "U", "D", "F" 중 하나를 추가 하 여 생성 된 ID를 단추에 대해 생성 된 이미지 또는 "X" (예, 다운 치중 하 고 사용 하지 않도록 설정)에 단추 캡션에 사용 되는 문자열에 3 단계. 단추 캡션에 대 한 " **MYIMAGE**," Id 수는 예를 들어 " **MYIMAGEU**," " **MYIMAGED**," " **MYIMAGEF**," 및 " **MYIMAGEX**. " 하면 **해야** 큰따옴표 안의 프로그램 비트맵의 ID를 지정 합니다. 그렇지 않은 경우 리소스 편집기에서 리소스에는 정수를 할당 하 고 이미지를 로드할 때 MFC 실패 합니다.  
  
5.  응용 프로그램의 대화 상자 클래스에 (에서 파생 된 `CDialog`), 추가 `CBitmapButton` 멤버 개체입니다.  
  
6.  에 `CDialog` 개체의 [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) 루틴을 호출은 `CBitmapButton` 개체의 [AutoLoad](#autoload) 단추의 컨트롤 ID의 매개 변수로 사용 하 여 작동할 및 `CDialog` 개체의 **이** 포인터입니다.  
  
 와 같은 Windows 알림 메시지를 처리 하려면 **BN_CLICKED**를 해당 부모 스 비트맵 단추 컨트롤에서 보낸, (클래스에서 파생 되는 일반적으로 **CDialog)** 에 추가 `CDialog`-파생 된 각 메시지에 대 한 메시지 맵 항목 및 메시지 처리기 멤버 함수는 개체입니다. 보낸 알림의 `CBitmapButton` 전송한 것과 동일 하 게 한 [CButton](../../mfc/reference/cbutton-class.md) 개체입니다.  
  
 클래스 [CToolBar](../../mfc/reference/ctoolbar-class.md) 비트맵 단추에는 다른 방식을 사용 합니다.  
  
 대 한 자세한 내용은 `CBitmapButton`, 참조 [컨트롤](../../mfc/controls-mfc.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="autoload"></a>  CBitmapButton::AutoLoad  
 대화 상자에서 단추의 개체와 연결 된 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 비트맵에 맞게 단추 크기를 조정 합니다.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 단추의 컨트롤 id입니다.  
  
 `pParent`  
 단추를 소유 하는 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 `AutoLoad` 소유자 그리기 단추는 비트맵 단추와 대화 상자에서 초기화 하는 함수입니다. 이 함수를 사용 하기 위한 지침은 대 한 설명에는 `CBitmapButton` 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton  
 
          `CBitmapButton` 개체를 만듭니다.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>설명  
 C + +를 만든 후 `CBitmapButton` 개체, 호출 [CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고에 연결 하는 `CBitmapButton` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps  
 리소스 이름 또는 ID 번호 또는 사용할 수 없는 경우를 식별 하는 비트맵 이미지를 로드 하려는 경우이 함수를 사용 하 여는 `AutoLoad` 예를 들어 대화 상자에 속하지 않는 하는 비트맵 단추 만들어지기 때문에 작동 합니다.  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszBitmapResource*  
 일반적인 경우는 비트맵 단추 또는 상태 "를" 비트맵의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. 필수.  
  
 *lpszBitmapResourceSel*  
 비트맵 단추 선택에 대 한 비트맵의 이름을 포함 하는 null로 끝나는 문자열 또는 "아래쪽" 상태를 가리킵니다. 되었을 **NULL**합니다.  
  
 *lpszBitmapResourceFocus*  
 상태는 비트맵 단추에 대 한 비트맵의 이름을 포함 하는 null로 끝나는 문자열을 가리키는 데 사용 됩니다. 되었을 **NULL**합니다.  
  
 *lpszBitmapResourceDisabled*  
 비트맵 단추의 사용할 수 없는 상태에 대 한 비트맵의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다. 되었을 **NULL**합니다.  
  
 *nIDBitmapResource*  
 일반적인 경우는 비트맵 단추 또는 상태 "를" 비트맵 리소스의 리소스 ID 번호를 지정합니다. 필수.  
  
 *nIDBitmapResourceSel*  
 비트맵 단추를 선택 하거나 "아래" 상태 비트맵 리소스의 리소스 ID 번호를 지정 합니다. 0 일 수 있습니다.  
  
 *nIDBitmapResourceFocus*  
 비트맵 단추 포커스가 있는 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정합니다. 0 일 수 있습니다.  
  
 *nIDBitmapResourceDisabled*  
 비트맵 단추의 사용할 수 없는 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정합니다. 0 일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent  
 비트맵 단추는 비트맵의 크기를 조정 하려면이 함수를 호출 합니다.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLTEST](../../visual-cpp-samples.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)

