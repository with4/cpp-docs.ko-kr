---
title: "CHwndRenderTarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::CHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::Attach
- AFXRENDERTARGET/CHwndRenderTarget::CheckWindowState
- AFXRENDERTARGET/CHwndRenderTarget::Create
- AFXRENDERTARGET/CHwndRenderTarget::Detach
- AFXRENDERTARGET/CHwndRenderTarget::GetHwnd
- AFXRENDERTARGET/CHwndRenderTarget::GetHwndRenderTarget
- AFXRENDERTARGET/CHwndRenderTarget::ReCreate
- AFXRENDERTARGET/CHwndRenderTarget::Resize
- AFXRENDERTARGET/CHwndRenderTarget::m_pHwndRenderTarget
dev_langs:
- C++
helpviewer_keywords:
- CHwndRenderTarget class
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1af6795e89c995ba6b5a7b094f06b0aea776f561
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="chwndrendertarget-class"></a>CHwndRenderTarget 클래스
ID2D1HwndRenderTarget에 대 한 래퍼입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHwndRenderTarget::CHwndRenderTarget](#chwndrendertarget)|HWND에서 CHwndRenderTarget 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHwndRenderTarget::Attach](#attach)|기존 연결 개체를 대상 인터페이스를 렌더링 합니다.|  
|[CHwndRenderTarget::CheckWindowState](#checkwindowstate)|이 렌더링 대상과 연결 된 HWND가 내포 되었는지 여부를 나타냅니다.|  
|[CHwndRenderTarget::Create](#create)|창에 연결 된 렌더링 대상을 만듭니다.|  
|[CHwndRenderTarget::Detach](#detach)|렌더링 대상 인터페이스 개체에서 분리|  
|[CHwndRenderTarget::GetHwnd](#gethwnd)|대상을 렌더링 하는이 연결 된 HWND를 반환 합니다.|  
|[CHwndRenderTarget::GetHwndRenderTarget](#gethwndrendertarget)|ID2D1HwndRenderTarget 인터페이스를 반환 합니다.|  
|[CHwndRenderTarget::ReCreate](#recreate)|창에 연결 된 렌더링 대상을 다시 만듭니다.|  
|[CHwndRenderTarget::Resize](#resize)|지정 된 픽셀 크기로 렌더링 대상의 크기를 변경합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget *](#operator_id2d1hwndrendertarget_star)|ID2D1HwndRenderTarget 인터페이스를 반환 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CHwndRenderTarget::m_pHwndRenderTarget](#m_phwndrendertarget)|ID2D1HwndRenderTarget 개체에 대 한 포인터입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxrendertarget.h  
  
##  <a name="attach"></a>CHwndRenderTarget::Attach  
 기존 연결 개체를 대상 인터페이스를 렌더링 합니다.  
  
```  
void Attach(ID2D1HwndRenderTarget* pTarget);
```  
  
### <a name="parameters"></a>매개 변수  
 `pTarget`  
 기존 렌더링 대상 인터페이스입니다. NULL 일 수 없습니다.  
  
##  <a name="checkwindowstate"></a>CHwndRenderTarget::CheckWindowState  
 이 렌더링 대상과 연결 된 HWND가 내포 되었는지 여부를 나타냅니다.  
  
```  
D2D1_WINDOW_STATE CheckWindowState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 와 연결 된 HWND 대상 렌더링 하는지 여부를 나타내는 값 폐색 됩니다.  
  
##  <a name="chwndrendertarget"></a>CHwndRenderTarget::CHwndRenderTarget  
 HWND에서 CHwndRenderTarget 개체를 만듭니다.  
  
```  
CHwndRenderTarget(HWND hwnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hwnd`  
 와 연결 된 HWND 렌더링 대상  
  
##  <a name="create"></a>CHwndRenderTarget::Create  
 창에 연결 된 렌더링 대상을 만듭니다.  
  
```  
BOOL Create(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 와 연결 된 HWND 렌더링 대상  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환  
  
##  <a name="detach"></a>CHwndRenderTarget::Detach  
 렌더링 대상 인터페이스 개체에서 분리  
  
```  
ID2D1HwndRenderTarget* Detach();
```  
  
### <a name="return-value"></a>반환 값  
 분리에 대 한 포인터는 대상 인터페이스를 렌더링 합니다.  
  
##  <a name="gethwnd"></a>CHwndRenderTarget::GetHwnd  
 대상을 렌더링 하는이 연결 된 HWND를 반환 합니다.  
  
```  
HWND GetHwnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 와 연결 된 HWND 대상을 렌더링 합니다.  
  
##  <a name="gethwndrendertarget"></a>CHwndRenderTarget::GetHwndRenderTarget  
 ID2D1HwndRenderTarget 인터페이스를 반환 합니다.  
  
```  
ID2D1HwndRenderTarget* GetHwndRenderTarget();
```  
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1HwndRenderTarget 인터페이스에 대 한 포인터입니다.  
  
##  <a name="m_phwndrendertarget"></a>CHwndRenderTarget::m_pHwndRenderTarget  
 ID2D1HwndRenderTarget 개체에 대 한 포인터입니다.  
  
```  
ID2D1HwndRenderTarget* m_pHwndRenderTarget;  
```  
  
##  <a name="operator_id2d1hwndrendertarget_star"></a>CHwndRenderTarget::operator ID2D1HwndRenderTarget *  
 ID2D1HwndRenderTarget 인터페이스를 반환 합니다.  
  
```  
operator ID2D1HwndRenderTarget*();
```   
  
### <a name="return-value"></a>반환 값  
 개체가 아직 초기화 되지 않은 경우에 NULL 또는 ID2D1HwndRenderTarget 인터페이스에 대 한 포인터입니다.  
  
##  <a name="recreate"></a>CHwndRenderTarget::ReCreate  
 창에 연결 된 렌더링 대상을 다시 만듭니다.  
  
```  
BOOL ReCreate(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 와 연결 된 HWND 렌더링 대상  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.  
  
##  <a name="resize"></a>CHwndRenderTarget::Resize  
 지정 된 픽셀 크기로 렌더링 대상의 크기를 변경합니다.  
  
```  
BOOL Resize(const CD2DSizeU& size);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 (장치 픽셀)에서 렌더링 대상의 새 크기  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 TRUE를 반환 합니다. 그렇지 않으면 FALSE를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)

