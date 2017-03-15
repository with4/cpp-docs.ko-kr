---
title: "CWinFormsControl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsControl class
- Windows Forms [C++], MFC support
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 49e24c04deda3df5683908fa9ca485cf7802214b
ms.lasthandoff: 02/24/2017

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
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|MFC 컨테이너에 있는 Windows Forms 컨트롤을 만듭니다.|  
|[CWinFormsControl::GetControl](#getcontrol)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Windows Forms 컨트롤에 대 한 핸들을 검색합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.|  
  
## <a name="remarks"></a>주의  
 `CWinFormsControl` 클래스는 Windows Forms 컨트롤을 호스팅하기 위한 기본 기능을 제공 합니다.  
  
 Windows Forms를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
 MFC 코드 창 핸들을 캐시 하지 않습니다 (일반적으로 저장 `m_hWnd`). 일부 Windows Forms 컨트롤 속성을 필요로 하는 기본 Win32 `Window` 제거 하 고 사용 하 여 다시 `DestroyWindow` 및 `CreateWindow`합니다. MFC Windows Forms 구현 핸들은 `Destroy` 및 `Create` 업데이트 하는 컨트롤의 이벤트는 `m_hWnd` 멤버입니다.  
  
> [!NOTE]
>  MFC Windows Forms 통합 MFC (AFXDLL 정의 되어 있는)를 사용 하 여 동적으로 링크 프로젝트 에서만 작동 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwinforms.h  
  
##  <a name="a-namecreatemanagedcontrola--cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 MFC 컨테이너에 있는 Windows Forms 컨트롤을 만듭니다.  
  
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
 만들 컨트롤의 데이터 형식입니다. 해야는 [형식](https://msdn.microsoft.com/en-us/library/system.type) 데이터 형식입니다.  
  
 `dwStyle`  
 컨트롤에 적용할 창 스타일입니다. 조합을 지정 [창 스타일](../../mfc/reference/window-styles.md)합니다. 현재 다음과 같은 스타일만 지원 됩니다: WS_TABSTOP, WS_VISIBLE, WS_DISABLED 및 WS_GROUP 합니다.  
  
 `rect`  
 A [RECT 구조체](../../mfc/reference/rect-structure1.md) 컨트롤의 왼쪽 위 및 오른쪽 아래 모퉁이의 좌표를 정의 하는 (첫 번째 오버 로드만).  
  
 `nPlaceHolderID`  
 리소스 편집기에서 배치 하는 정적 내부 소유자 컨트롤의 핸들입니다. 새로 만든된 Windows Forms 컨트롤에서 해당 위치, z-순서 및 스타일을 가정 하는 정적 컨트롤을 바꿉니다 (두 번째 오버 로드만).  
  
 `pParentWnd`  
 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 새로 만든된 컨트롤에 할당 될 리소스 ID.  
  
 `pControl`  
 연관 되어야 하는 Windows Forms 컨트롤의 인스턴스는 [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) 개체 (네 번째 오버 로드만).  
  
### <a name="return-value"></a>반환 값  
 성공 하면&0;이 아닌 값을 반환 합니다. 실패할 경우&0;을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 MFC 컨테이너에서.NET Framework Windows Forms 컨트롤을 인스턴스화합니다.  
  
 메서드의 첫 번째 오버 로드는.NET Framework 데이터 형식을 수락 `pType` MFC에는이 형식의 새 개체를 인스턴스화할 수 있도록 합니다. `pType`해야는 [형식](https://msdn.microsoft.com/en-us/library/system.type) 데이터 형식입니다.  
  
 메서드의 두 번째 오버 로드에 따라 Windows Forms 컨트롤을 만듭니다.는 `TManagedControl` 의 템플릿 매개 변수는 `CWinFormsControl` 클래스입니다. 크기와 컨트롤의 위치는 기반는 `RECT` 메서드에 전달 하는 구조입니다. 만 `dwStyle` 스타일에 대 한 중요 합니다.  
  
 메서드의 세 번째 오버 로드는 정적 컨트롤, 삭제 하며 해당 위치, z-순서 및 스타일을 대체 하는 Windows Forms 컨트롤을 만듭니다. 정적 컨트롤은 Windows Forms 컨트롤에 대 한 자리 표시자 역할만합니다. 이 오버 로드 하 여 스타일을 결합 하 여 컨트롤을 만들 때 `dwStyle` 정적 컨트롤의 리소스 스타일을 사용 합니다.  
  
 메서드의 네 번째 오버 로드를 사용 하면 이미 인스턴스화된 Windows Forms 컨트롤에 전달할 수 `pControl` 을 MFC 래핑하는 합니다. 와 같은 형식 이어야는 `TManagedControl` 의 템플릿 매개 변수는 `CWinFormsControl` 클래스입니다.  
  
 참조 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 대 한 Windows Form을 사용 하 여 샘플을 제어 합니다.  
  
##  <a name="a-namecwinformscontrola--cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 MFC Windows Forms 컨트롤 래퍼 개체를 생성 합니다.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 Windows Forms 컨트롤을 인스턴스화하 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.  
  
##  <a name="a-namegetcontrola--cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinFormsControl::GetControl  
 Windows Forms 컨트롤에 대 한 포인터를 검색합니다.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows Forms 컨트롤에 대 한 포인터를 반환합니다.  
  
### <a name="example"></a>예제  
  참조 [CWinFormsControl::CreateManagedControl](#createmanagedcontrol)합니다.  
  
##  <a name="a-namegetcontrolhandlea--cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Windows Forms 컨트롤에 대 한 핸들을 검색합니다.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows Forms 컨트롤에 대 한 핸들을 반환합니다.  
  
### <a name="remarks"></a>주의  
 `GetControlHandle`.NET Framework 컨트롤 속성에 저장 된 창 핸들을 반환 하는 도우미 메서드입니다. 창 핸들 값에 복사 됩니다 [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) 호출 하는 동안 [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach)합니다.  
  
##  <a name="a-nameoperator-gta--cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 대체 [CWinFormsControl::GetControl](#getcontrol) 식에 있습니다.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>주의  
 이 연산자를 대체 하는 편리한 구문을 제공 `GetControl` 식에 있습니다.  
  
 Windows Forms에 대 한 자세한 내용은 참조 하십시오. [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)합니다.  
  
##  <a name="a-nameoperatortmanagedcontrola--cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>주의  
 이 연산자를 전달 `CWinFormsControl<``TManagedControl``>` 에 Windows Forms 컨트롤에 대 한 포인터를 허용 하는 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWinFormsDialog 클래스](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)

