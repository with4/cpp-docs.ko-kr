---
title: CPaintDC 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaintDC
- AFXWIN/CPaintDC
- AFXWIN/CPaintDC::CPaintDC
- AFXWIN/CPaintDC::m_ps
- AFXWIN/CPaintDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CPaintDC [MFC], CPaintDC
- CPaintDC [MFC], m_ps
- CPaintDC [MFC], m_hWnd
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 496c06fe7550598eeeb4136b233f39079d7425e9
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078221"
---
# <a name="cpaintdc-class"></a>CPaintDC 클래스
파생 된 디바이스 컨텍스트 클래스 [CDC](../../mfc/reference/cdc-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPaintDC : public CDC  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPaintDC::CPaintDC](#cpaintdc)|생성 된 `CPaintDC` 에 지정 된 연결 [CWnd](../../mfc/reference/cwnd-class.md)합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CPaintDC::m_ps](#m_ps)|포함 된 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) 클라이언트 영역을 그리는 데 사용 합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND` 이 `CPaintDC` 개체를 연결 합니다.|  
  
## <a name="remarks"></a>설명  
 수행 된 [cwnd:: Beginpaint](../../mfc/reference/cwnd-class.md#beginpaint) 생성 시 및 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) 소멸 시.  
  
 A `CPaintDC` 개체에 응답 하는 경우에 사용할 수는 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지에 일반적으로 프로그램 `OnPaint` 메시지 처리기 멤버 함수입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CPaintDC`, 참조 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cpaintdc"></a>  CPaintDC::CPaintDC  
 생성 된 `CPaintDC` 개체를 응용 프로그램 창 그리기를 위해 준비 하 고 저장는 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) 구조에서 [m_ps](#m_ps) 멤버 변수입니다.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 가리키는 `CWnd` 개체는 `CPaintDC` 개체가 속한 합니다.  
  
### <a name="remarks"></a>설명  
 예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) 호출이 실패 합니다. 장치 컨텍스트에 Windows 이미 할당 된 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있는 수 있습니다. Windows에서 언제 든 지 사용할 수 있는 5 개의 일반적인 디스플레이 컨텍스트를 위한 응용 프로그램 완료 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#97](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CPaintDC::m_hWnd  
 `HWND` 이 `CPaintDC` 개체를 연결 합니다.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>설명  
 *m_hWnd* 형식의 보호 된 변수는 `HWND`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#98](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>  CPaintDC::m_ps  
 `m_ps` 형식의 공용 멤버 변수 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)합니다.  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>설명  
 `PAINTSTRUCT` 에 전달 되 고 여 채울 [cwnd:: Beginpaint](../../mfc/reference/cwnd-class.md#beginpaint)합니다.  
  
 `PAINTSTRUCT` 응용 프로그램의 연결 된 창의 클라이언트 영역을 그리는 데 사용 하는 정보를 포함 한 `CPaintDC` 개체입니다.  
  
 장치 컨텍스트 핸들을 통해 액세스할 수 있는지 참고는 `PAINTSTRUCT`합니다. 그러나 핸들을 통해 직접 액세스할 수 있습니다는 `m_hDC` 멤버 변수는 `CPaintDC` 에서 상속 `CDC`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPaintDC::m_hWnd](#m_hwnd)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



