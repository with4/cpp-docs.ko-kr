---
title: "CWinFormsControl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2e6bf46cf28c3bca3d71f85cdd681745a0379bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cwinformscontrol-class"></a>CWinFormsControl 클래스
Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>매개 변수  
 `TManagedControl`  
 MFC 응용 프로그램에 표시 되는.NET Framework Windows Forms 컨트롤입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|MFC Windows Forms 컨트롤 래퍼 개체를 생성 합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC 컨테이너에는 Windows Forms 컨트롤을 만듭니다.|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms 컨트롤에 대 한 핸들을 검색합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.|  
  
## <a name="remarks"></a>설명  
 `CWinFormsControl` 클래스는 Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공 합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
 MFC 코드 창 핸들을 캐시 하지 않습니다 (일반적으로 저장 `m_hWnd`). 일부 Windows Forms 컨트롤 속성을 필요로 하는 기본 Win32 `Window` 소멸을 사용 하 여 다시 `DestroyWindow` 및 `CreateWindow`합니다. MFC Windows Forms 구현 핸들의 `Destroy` 및 `Create` 업데이트 하려면 컨트롤의 이벤트는 `m_hWnd` 멤버입니다.  
  
> [!NOTE]
>  MFC Windows Forms 통합 (AFXDLL 정의 되어 있는) MFC에 동적으로 링크 되는 프로젝트 에서만 작동 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 MFC 컨테이너에는 Windows Forms 컨트롤을 만듭니다.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `pType`  
 만들 컨트롤의 데이터 형식입니다. 있어야는 [형식](https://msdn.microsoft.com/en-us/library/system.type) 데이터 형식입니다.  
  
 `dwStyle`  
 컨트롤에 적용할 창 스타일입니다. 조합을 지정할 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 현재 다음 스타일에만 지원 됩니다: WS_TABSTOP, WS_VISIBLE, WS_DISABLED 및 WS_GROUP 합니다.  
  
 `rect`  
 A [RECT 구조체](../../mfc/reference/rect-structure1.md) 컨트롤의 왼쪽 및 오른쪽 아래 모퉁이의 좌표를 정의 하는 (먼저 오버 로드만).  
  
 `nPlaceHolderID`  
 리소스 편집기에서 배치 하는 정적 내부 소유자 컨트롤의 핸들입니다. 새로 만든된 Windows Forms 컨트롤의 위치, z-순서 및 스타일을 가정 하는 정적 컨트롤을 대체 (두 번째 오버 로드만).  
  
 `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 새로 만든된 컨트롤에 할당할 리소스 ID.  
  
 `pControl`  
 연관 되어야 하는 Windows Forms 컨트롤의 인스턴스는 [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) 개체 (네 번째 오버 로드만).  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 값을 반환 합니다. 프로시저가 실패 하면 0을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 MFC 컨테이너에서.NET Framework Windows Forms 컨트롤을 인스턴스화합니다.  
  
 메서드의 첫 번째 오버 로드는.NET Framework 데이터 형식을 수락 `pType` MFC는이 형식의 새 개체를 인스턴스화할 수 있도록 합니다. `pType`있어야는 [형식](https://msdn.microsoft.com/en-us/library/system.type) 데이터 형식입니다.  
  
 메서드의 두 번째 오버 로드에 따라 Windows Forms 컨트롤을 만듭니다.는 `TManagedControl` 템플릿 매개 변수에 `CWinFormsControl` 클래스입니다. 크기와 컨트롤의 위치 기반는 `RECT` 메서드에 전달 하는 구조입니다. 만 `dwStyle` 스타일에 대 한 중요 합니다.  
  
 메서드의 세 번째 오버 로드는 정적 컨트롤을 제거 하 고 해당 위치, z-순서 및 스타일을 가정 하면 대체 하는 Windows Forms 컨트롤을 만듭니다. 정적 컨트롤은 Windows Forms 컨트롤에 대 한 자리 표시자 역할만합니다. 이 오버 로드에서 스타일을 결합 컨트롤을 만들 때 `dwStyle` 정적 컨트롤의 리소스 스타일을 사용 합니다.  
  
 메서드의 네 번째 오버 로드를 사용 하는 이미 인스턴스화된 Windows Forms 컨트롤에 전달할 수 있도록 `pControl` 을 MFC 래핑하는 합니다. 동일한 형식 이어야 합니다는 `TManagedControl` 템플릿 매개 변수에 `CWinFormsControl` 클래스입니다.  
  
 참조 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Form을 사용 하는 샘플에 대 한 제어 합니다.  
  
##  <a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 MFC Windows Forms 컨트롤 래퍼 개체를 생성 합니다.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>설명  
 호출 하는 경우 Windows Forms 컨트롤을 인스턴스화하 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.  
  
##  <a name="getcontrol"></a>CWinFormsControl::GetControl  
 Windows Forms 컨트롤에 대 한 포인터를 검색합니다.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows Forms 컨트롤에 대 한 포인터를 반환합니다.  
  
### <a name="example"></a>예  
  참조 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.  
  
##  <a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Windows Forms 컨트롤에 대 한 핸들을 검색합니다.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows Forms 컨트롤에 대 한 핸들을 반환합니다.  
  
### <a name="remarks"></a>설명  
 `GetControlHandle`.NET Framework 컨트롤 속성에 저장 된 창 핸들을 반환 하는 도우미 메서드입니다. 창 핸들 값 복사할 [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) 호출 하는 동안 [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)합니다.  
  
##  <a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>설명  
 이 연산자를 대체 하는 편리한 구문 제공 `GetControl` 식에 있습니다.  
  
 Windows Forms에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>설명  
 이 연산자 전달 `CWinFormsControl<TManagedControl>` 에 Windows Forms 컨트롤에 대 한 포인터를 허용 하는 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWinFormsDialog 클래스](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)
