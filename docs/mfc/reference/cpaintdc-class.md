---
title: "CPaintDC 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- OnPaint handler
- WM_PAINT message
- CPaintDC class
ms.assetid: 7e245baa-bf9b-403e-a637-7218adf28fab
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b781db7d4a6676e6fc6ad5df7553b9c9a0154ab9
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
  
|이름|설명|  
|----------|-----------------|  
|[CPaintDC::m_hWnd](#m_hwnd)|`HWND` 이 `CPaintDC` 개체를 연결 합니다.|  
  
## <a name="remarks"></a>주의  
 수행 된 [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint) 생성 시 및 [CWnd::EndPaint](../../mfc/reference/cwnd-class.md#endpaint) 소멸 시.  
  
 A `CPaintDC` 개체에 대 한 응답 하는 경우에 사용 수는 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지에 일반적으로 프로그램 `OnPaint` 메시지 처리기 멤버 함수입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CPaintDC`, 참조 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CPaintDC`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cpaintdc"></a>CPaintDC::CPaintDC  
 생성 한 `CPaintDC` 개체를 응용 프로그램 창에 대 한 그리기를 준비 하 고 저장는 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md) 구조에서 [m_ps](#m_ps) 멤버 변수입니다.  
  
```  
explicit CPaintDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 가리키는 `CWnd` 개체는 `CPaintDC` 개체가 속한 합니다.  
  
### <a name="remarks"></a>주의  
 예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) 호출이 실패 합니다. 장치 컨텍스트에 하지 못할 경우 Windows에 이미 할당 된 모든 사용 가능한 장치 컨텍스트. 응용 프로그램은 Windows 아래에서 언제 든 지 사용할 수 있는&5; 개의 일반적인 디스플레이 컨텍스트를 위한 경쟁 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&97;](../../mfc/codesnippet/cpp/cpaintdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CPaintDC::m_hWnd  
 `HWND` 이 `CPaintDC` 개체를 연결 합니다.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>주의  
 `m_hWnd`보호 되는 유형의 변수 `HWND`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&98;](../../mfc/codesnippet/cpp/cpaintdc-class_2.cpp)]  
  
##  <a name="m_ps"></a>CPaintDC::m_ps  
 `m_ps`형식의 공용 멤버 변수 [PAINTSTRUCT](../../mfc/reference/paintstruct-structure.md)합니다.  
  
```  
PAINTSTRUCT m_ps;  
```  
  
### <a name="remarks"></a>주의  
 `PAINTSTRUCT` 에 전달 되 고 작성 [CWnd::BeginPaint](../../mfc/reference/cwnd-class.md#beginpaint)합니다.  
  
 `PAINTSTRUCT` 응용 프로그램에 연결 된 창의 클라이언트 영역을 그리는 데 사용 하는 정보를 포함 한 `CPaintDC` 개체입니다.  
  
 장치 컨텍스트 핸들을 통해 액세스할 수 있는지 참고는 `PAINTSTRUCT`합니다. 그러나 핸들을 통해 직접 액세스할 수 있습니다는 `m_hDC` 멤버 변수는 `CPaintDC` 에서 상속 `CDC`합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CPaintDC::m_hWnd](#m_hwnd)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDI](../../visual-cpp-samples.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




