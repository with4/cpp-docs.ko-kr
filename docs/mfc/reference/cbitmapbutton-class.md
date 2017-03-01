---
title: "CBitmapButton 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapButton
dev_langs:
- C++
helpviewer_keywords:
- buttons, bitmap
- CBitmapButton class
- bitmaps, button controls
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
caps.latest.revision: 22
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 16d39cb380b75e6dcef71dda01626f120d5c12fb
ms.lasthandoff: 02/24/2017

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
|[CBitmapButton::AutoLoad](#autoload)|대화 상자의 단추에에서의 한 개체에 연결에서 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 단추 비트맵에 맞게 크기를 지정 합니다.|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|응용 프로그램의 리소스 파일에서 하나 이상의 명명 된 비트맵 리소스를 로드 하는 개체에 비트맵을 연결 하 여 개체를 초기화 합니다.|  
|[CBitmapButton::SizeToContent](#sizetocontent)|단추 비트맵에 맞게 크기를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 `CBitmapButton`개체 단추 간주 될 수 있는 여러 상태에 대 한 이미지를 포함 하는 최대&4; 개의 비트맵에 포함: 업 (또는 보통), 아래쪽 또는 (선택) 치중 하 고 사용 하지 않도록 설정 합니다. 첫 번째 비트맵에만 필수 사항입니다. 다른 항목은 선택 사항입니다.  
  
 비트맵 단추 이미지는 이미지 자체 뿐 아니라 이미지 주위에 테두리가 포함 됩니다. 테두리는 일반적으로 한 역할 단추의 상태를 표시 합니다. 예를 들어 포커스가 있는 상태에 대 한 비트맵은 일반적으로 같은 테두리 또는 테두리에 굵은 실선에서 파선된 사각형 삽입 하지만 최신 상태에 대 한입니다. 비트맵은 disabled 일반적으로 상태에 대 한 유사 하나 놓여 않았으나 낮은 대비 (예: 흐리게 표시 되거나 회색으로 표시 된 메뉴 선택)에 대 한 합니다.  
  
 이러한 비트맵의 크기나 수 있지만 최신 상태에 대 한 비트맵으로 같은 크기로 것 처럼 처리 됩니다 모든.  
  
 다양 한 응용 프로그램은 비트맵 이미지의 다양 한 조합을 요구 합니다.  
  
|위로|아래로|포커스 있음|사용 안 함|응용 프로그램|  
|--------|----------|-------------|--------------|-----------------|  
|×||||Bitmap|  
|×|×|||없이 단추 **WS_TABSTOP** 스타일|  
|×|×|×|×|모든 상태와 대화 상자 단추|  
|×|×|×||대화 상자 단추와 **WS_TABSTOP** 스타일|  
  
 비트맵 단추 컨트롤을 만들 때 설정 된 **BS_OWNERDRAW** 소유자가 그린 단추 인지를 지정 하는 스타일입니다. 이 인해 보내도록 Windows는 `WM_MEASUREITEM` 및 `WM_DRAWITEM` 단추;에 대 한 메시지 이러한 메시지를 처리 하 고 있습니다 단추의 모양을 관리 하는 프레임 워크입니다.  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>창의 클라이언트 영역에는 비트맵 단추 컨트롤을 만들려면  
  
1.  단추에 대해&1; ~&4; 개의 비트맵 이미지를 만듭니다.  
  
2.  생성 된 [CBitmapButton](#cbitmapbutton) 개체입니다.  
  
3.  호출 된 [만들기](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고에 연결 하는 함수는 `CBitmapButton` 개체입니다.  
  
4.  호출 된 [LoadBitmaps](#loadbitmaps) 비트맵 단추를 생성 한 후에 비트맵 리소스를 로드 하는 멤버 함수입니다.  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>대화 상자에는 비트맵 단추 컨트롤을 포함 하려면  
  
1.  단추에 대해&1; ~&4; 개의 비트맵 이미지를 만듭니다.  
  
2.  비트맵 단추를 원하는 위치로 옮깁니다 소유자 그리기 단추가 있는 대화 상자 템플릿을 만듭니다. 서식 파일에 있는 단추의 크기를 중요 하지 않습니다.  
  
3.  와 같은 값으로 단추의 캡션을 설정 " **MYIMAGE**"와 같은 단추에 대 한 기호를 정의 하 고 **IDC_MYIMAGE**합니다.  
  
4.  응용 프로그램의 리소스 스크립트에 문자 "U", "D", "F" 중 하나를 추가 하 여 생성 된 ID를 단추에 대해 생성 된 이미지의 각 또는 "X" (예, 아래로 포커스 및 사용 안 함)에 단추 캡션에 사용 되는 문자열에 3 단계. 단추 캡션을 대 한 " **MYIMAGE**," Id 것 예를 들어 " **MYIMAGEU**," " **MYIMAGED**," " **MYIMAGEF**," 및 " **MYIMAGEX**." 하면 **해야** 큰따옴표 안의 프로그램 비트맵의 ID를 지정 합니다. 그렇지 않은 경우 리소스 편집기에서 리소스에는 정수를 할당 하 고 이미지를 로드할 때 MFC 실패 합니다.  
  
5.  응용 프로그램의 대화 상자 클래스에서 (에서 파생 된 `CDialog`), 추가 `CBitmapButton` 멤버 개체입니다.  
  
6.  에 `CDialog` 개체의 [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) 루틴을 호출은 `CBitmapButton` 개체의 [AutoLoad](#autoload) 함수를 단추 컨트롤 ID를 매개 변수로 사용 하 여 고 `CDialog` 개체의 **이** 포인터입니다.  
  
 와 같은 Windows 알림 메시지를 처리 하려는 경우 **BN_CLICKED**비트맵 단추 컨트롤을 해당 부모가 보내는 (클래스에서 파생 되는 일반적으로 **CDialog)**를에 추가 `CDialog`-각 메시지에 대 한 개체는 메시지 맵 항목 및 메시지-처리기 멤버 함수를 파생 합니다. 보낸 알림의 `CBitmapButton` 개체에서 보낸 것과 동일는 [CButton](../../mfc/reference/cbutton-class.md) 개체입니다.  
  
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
  
##  <a name="a-nameautoloada--cbitmapbuttonautoload"></a><a name="autoload"></a>CBitmapButton::AutoLoad  
 대화 상자의 단추에에서의 한 개체에 연결에서 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 단추 비트맵에 맞게 크기를 지정 합니다.  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 단추 컨트롤의 id입니다.  
  
 `pParent`  
 단추를 소유 하는 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 된 `AutoLoad` 는 소유자 그리기 단추는 비트맵 단추와 대화 상자에서 초기화 하는 함수입니다. 이 함수를 사용 하는 것에 대 한 지침은 대 한 설명에는 `CBitmapButton` 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog #&75;](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="a-namecbitmapbuttona--cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 
          `CBitmapButton` 개체를 만듭니다.  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>주의  
 C + +를 만든 후 `CBitmapButton` 개체, 호출 [CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고에 연결 하는 `CBitmapButton` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog #&57;](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="a-nameloadbitmapsa--cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 사용할 수 없는 경우 또는 자원 이름 또는 ID 번호로 식별 하는 비트맵 이미지를 로드 하려는 경우이 함수를 사용 하 여는 `AutoLoad` 예를 들어 대화 상자에 속하지 않는 하는 비트맵 단추 만들어지기 때문에 작동 합니다.  
  
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
 일반적인 경우는 비트맵 단추 또는 상태 "를" 비트맵의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. 필수 요소.  
  
 *lpszBitmapResourceSel*  
 비트맵 단추 선택에 대 한 비트맵의 이름이 포함 된 null로 끝나는 문자열에 또는 "down" 상태를 가리킵니다. 수 **NULL**합니다.  
  
 *lpszBitmapResourceFocus*  
 상태는 비트맵 단추에 대 한 비트맵의 이름을 포함 하는 null로 끝나는 문자열을 가리키는 데 사용 됩니다. 수 **NULL**합니다.  
  
 *lpszBitmapResourceDisabled*  
 비트맵 단추 사용 안 함된 상태에 대 한 비트맵의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. 수 **NULL**합니다.  
  
 *nIDBitmapResource*  
 일반적인 경우는 비트맵 단추 또는 상태 "를" 비트맵 리소스의 리소스 ID 번호를 지정합니다. 필수 요소.  
  
 *nIDBitmapResourceSel*  
 비트맵 단추 선택에 대 한 또는 "down" 상태로 비트맵 리소스의 리소스 ID 번호를 지정 합니다. 0 일 수 있습니다.  
  
 *nIDBitmapResourceFocus*  
 비트맵 단추의 포커스가 있는 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정합니다. 0 일 수 있습니다.  
  
 *nIDBitmapResourceDisabled*  
 비트맵 단추 사용 안 함된 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정합니다. 0 일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog #&58;](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="a-namesizetocontenta--cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 비트맵의 크기를 비트맵 단추 크기를 조정 하려면이 함수를 호출 합니다.  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog #&59;](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLTEST](../../visual-cpp-samples.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


