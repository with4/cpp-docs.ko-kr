---
title: "CAnimateCtrl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimateCtrl
- AFXCMN/CAnimateCtrl
- AFXCMN/CAnimateCtrl::CAnimateCtrl
- AFXCMN/CAnimateCtrl::Close
- AFXCMN/CAnimateCtrl::Create
- AFXCMN/CAnimateCtrl::CreateEx
- AFXCMN/CAnimateCtrl::IsPlaying
- AFXCMN/CAnimateCtrl::Open
- AFXCMN/CAnimateCtrl::Play
- AFXCMN/CAnimateCtrl::Seek
- AFXCMN/CAnimateCtrl::Stop
dev_langs: C++
helpviewer_keywords:
- CAnimateCtrl [MFC], CAnimateCtrl
- CAnimateCtrl [MFC], Close
- CAnimateCtrl [MFC], Create
- CAnimateCtrl [MFC], CreateEx
- CAnimateCtrl [MFC], IsPlaying
- CAnimateCtrl [MFC], Open
- CAnimateCtrl [MFC], Play
- CAnimateCtrl [MFC], Seek
- CAnimateCtrl [MFC], Stop
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58918a45daa1a6f64c160d79f52503e3a3c61cff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="canimatectrl-class"></a>CAnimateCtrl 클래스
Windows 공용 애니메이션 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|`CAnimateCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|AVI 클립을 닫습니다.|  
|[CAnimateCtrl::Create](#create)|애니메이션 컨트롤을 만들고에 연결 된 `CAnimateCtrl` 개체입니다.|  
|[CAnimateCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 애니메이션 컨트롤을 만들고에 연결 된 `CAnimateCtrl` 개체입니다.|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Audio-video 인터리빙 된 (AVI) 클립 재생 되 고 있는지 여부를 나타냅니다.|  
|[CAnimateCtrl::Open](#open)|AVI 클립 파일이 나 리소스에서 열리고 첫 번째 프레임을 표시 합니다.|  
|[CAnimateCtrl::Play](#play)|AVI 클립 없이 소리를 재생합니다.|  
|[CAnimateCtrl::Seek](#seek)|AVI 클립의 선택한 단일 프레임을 표시합니다.|  
|[CAnimateCtrl::Stop](#stop)|AVI 클립 재생을 중지 합니다.|  
  
## <a name="remarks"></a>설명  
 이 컨트롤 (및 따라서는 `CAnimateCtrl` 클래스) 이상 Windows 95, Windows 98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 애니메이션 컨트롤은 클립 AVI (오디오 비디오 인터리브) 형식으로 표시 되는 사각형 창은 — 표준 Windows 비디오/오디오 형식입니다. AVI 클립 일련의 영화 같은 비트맵 프레임입니다.  
  
 애니메이션 컨트롤 간단한 AVI 클립을 재생할 수 있습니다. 특히, 클립 애니메이션 컨트롤에서 재생할 수에 다음 요구 사항을 충족 해야 합니다.  
  
-   정확히 하나의 비디오 스트림 이어야 하며 하나 이상의 프레임 있어야 합니다.  
  
-   에 있을 수 최대 두 개의 스트림을 파일 (일반적으로 다른 스트림에 있는 경우는 오디오 스트림, 애니메이션 컨트롤은 오디오 정보를 무시 하지만).  
  
-   클립 압축 하거나 RLE8 압축으로 압축 해야 합니다.  
  
-   비디오 스트림에서 없습니다 색상표 변경이 허용 됩니다.  
  
 AVI 클립 AVI 리소스로 응용 프로그램에 추가 하거나 AVI 별도 파일로 응용 프로그램와 함께 보낼 수 있습니다.  
  
 스레드가 계속 AVI 클립 표시 되는 동안 실행을 하기 때문에 시간이 오래 걸리는 작업 중 시스템 작업을 나타내기 위해 애니메이션 컨트롤에 대 한 하나의 일반적인 용도가입니다. 예를 들어, 파일 탐색기의 찾기 대화 상자에서 파일에 대 한 시스템 검색으로 움직이는 돋보기를 표시합니다.  
  
 만드는 경우는 `CAnimateCtrl` 상자 또는에서 대화 상자 편집기를 사용 하 여 대화 상자 리소스를 자동으로 소멸 됩니다는 사용자가 대화 상자를 닫을 때 대화 내 개체입니다.  
  
 만드는 경우는 `CAnimateCtrl` 개체 창으로 삭제 해야 할 수 있습니다. 만드는 경우는 `CAnimateCtrl` 개체 스택, 자동으로 삭제 됩니다. 만드는 경우는 `CAnimateCtrl` 개체를 사용 하 여 힙에 **새** 호출 해야 함수를 **삭제** 삭제할 개체에 있습니다. 새 클래스를 파생 하는 경우 `CAnimateCtrl` 및 해당 클래스에는 메모리 할당, 재정의 `CAnimateCtrl` 할당을 삭제 하는 소멸자입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CAnimateCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CAnimateCtrl 사용 하 여](../../mfc/using-canimatectrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 `CAnimateCtrl` 개체를 생성합니다.  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>설명  
 호출 해야 합니다는 [만들기](#create) 만들면 개체에 다른 작업을 수행 하기 전에 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCControlLadenDialog#56](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="close"></a>CAnimateCtrl::Close  
 애니메이션 컨트롤 (있는 경우)에서 이전에 연 AVI 클립 닫고 메모리에서 제거 합니다.  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
##  <a name="create"></a>CAnimateCtrl::Create  
 애니메이션 컨트롤을 만들고에 연결 된 `CAnimateCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 애니메이션 컨트롤의 스타일을 지정합니다. 애니메이션 컨트롤 스타일 및 아래 설명 섹션에 설명 된 스타일에 설명 된 windows의 조합을 적용 [애니메이션 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761886) Windows sdk에서입니다.  
  
 `rect`  
 애니메이션 컨트롤의 위치와 크기를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
 `pParentWnd`  
 애니메이션 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL입니다.**  
  
 `nID`  
 애니메이션 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CAnimateCtrl` 두 단계를 수행에서 합니다. 먼저 생성자를 호출 하 고 호출 **만들기**, 애니메이션 컨트롤을 만들고에 연결 하는 `CAnimateCtrl` 개체입니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 애니메이션 컨트롤을 합니다.  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** 일반적으로  
  
- **WS_DISABLED** 거의  
  
 애니메이션 컨트롤 확장된 창 스타일을 사용 하려면 호출 [CreateEx](#createex) 대신 **만들기**합니다.  
  
 위에 나열 된 창 스타일, 외에도 애니메이션 컨트롤 스타일 중 하나 이상을 애니메이션 컨트롤에 적용 하는 것이 좋습니다. 자세한 내용은 Windows SDK에서 참조 [애니메이션 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761886)합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
##  <a name="createex"></a>CAnimateCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CAnimateCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `dwStyle`  
 애니메이션 컨트롤의 스타일을 지정합니다. 에 설명 된 애니메이션 컨트롤 스타일 및 창의 조합을 적용 [애니메이션 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb761886) Windows sdk에서입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_**합니다.  
  
##  <a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Audio-video 인터리빙 된 (AVI) 클립 재생 되 고 있는지 여부를 나타냅니다.  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `true`AVI 클립; 재생 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="open"></a>CAnimateCtrl::Open  
 AVI 클립을 열고 해당 첫 번째 프레임을 표시 하려면이 함수를 호출 합니다.  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszFileName`  
 A `CString` 개체나 AVI 파일의 이름이 나 AVI 리소스의 이름을 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 매개 변수가 **NULL**, 시스템이 있는 경우 애니메이션 컨트롤에 대 한 이전에 연 AVI 클립을 닫습니다.  
  
 `nID`  
 AVI 리소스 식별자입니다. 이 매개 변수가 **NULL**, 시스템이 있는 경우 애니메이션 컨트롤에 대 한 이전에 연 AVI 클립을 닫습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 AVI 리소스 애니메이션 컨트롤을 생성 하는 모듈에서 로드 됩니다.  
  
 **열고** AVI 클립;에서 소리를 지원 하지 않습니다 자동 AVI 클립을 열 수 있습니다.  
  
 애니메이션 컨트롤에 있는 경우는 `ACS_AUTOPLAY` 스타일 애니메이션 컨트롤이 자동으로 시작 열리는 직후 클립을 재생 합니다. 스레드가 계속 실행 하는 동안 백그라운드에서 클립 재생을 계속 됩니다. 클립 완료 되 면 재생 하 고,이 자동으로 반복 됩니다.  
  
 애니메이션 컨트롤에 있는 경우는 `ACS_CENTER` 스타일을 컨트롤에 AVI 클립은 가운데에 맞춰지고 컨트롤의 크기가 변경 되지 것입니다. 애니메이션 컨트롤에 없는 경우는 `ACS_CENTER` 스타일을 컨트롤 AVI 클립 AVI 클립에 있는 이미지의 크기에 열릴 때 크기가 조정 됩니다. 컨트롤의 왼쪽된 위 모퉁이의 위치 변경 되지 않습니다, 컨트롤의 크기에만.  
  
 애니메이션 컨트롤에 있는 경우는 `ACS_TRANSPARENT` 스타일을 첫 번째 프레임에 투명 한 배경을 사용 하 여 그려집니다에 지정 된 배경색 보다는 애니메이션 클립 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
##  <a name="play"></a>CAnimateCtrl::Play  
 애니메이션 컨트롤 AVI 클립을 재생 하는 데이 함수를 호출 합니다.  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFrom`  
 재생이 시작 되는 프레임의 0부터 시작 인덱스입니다. 값을 65536 보다 작거나 같아야 합니다. 0 이면 AVI 클립의 첫 번째 프레임으로 시작 하는 값입니다.  
  
 `nTo`  
 프레임의 0부터 시작 인덱스 위치 끝을 재생 합니다. 값을 65536 보다 작거나 같아야 합니다. 값은-1 = 마지막 프레임 AVI 클립에서 끝나야 합니다.  
  
 *nRep*  
 AVI 클립 재생 횟수입니다. 값은-1은 무기한 파일을 재생 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 컨트롤 스레드가 계속 실행 하는 동안 백그라운드에서 클립을 재생 됩니다. 애니메이션 컨트롤에 있는 경우 `ACS_TRANSPARENT` 스타일 AVI 클립 재생 될 애니메이션 클립에 지정 된 배경색 보다는 투명 한 배경을 사용 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
##  <a name="seek"></a>CAnimateCtrl::Seek  
 정적으로 AVI 클립의 단일 프레임을 표시 하려면이 함수를 호출 합니다.  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>매개 변수  
 `nTo`  
 표시할 프레임의 0부터 시작 인덱스입니다. 값을 65536 보다 작거나 같아야 합니다. 값이 0 AVI 클립의 첫 번째 프레임을 표시 하는 의미 합니다. 값이-1 AVI 클립의 마지막 프레임을 표시 하는 의미 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 애니메이션 컨트롤에 있는 경우 `ACS_TRANSPARENT` 스타일, 투명 한 배경을 사용 하 여 AVI 클립을 그려집니다에 지정 된 배경색 보다는 애니메이션 클립 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
##  <a name="stop"></a>CAnimateCtrl::Stop  
 AVI 클립 애니메이션 컨트롤에서 재생을 중지 하려면이 함수를 호출 합니다.  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CAnimateCtrl::CAnimateCtrl](#canimatectrl)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](message-map-macros-mfc.md#on_control)

