---
title: "CClientDC 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a92fb471ee30e725cd97bff6cbda8d551c0bc859
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cclientdc-class"></a>CClientDC 클래스
Windows 함수 호출을 맡고 [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871) 생성 시 및 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920) 소멸 시.  
  
## <a name="syntax"></a>구문  
  
```  
class CClientDC : public CDC  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CClientDC::CClientDC](#cclientdc)|생성 된 `CClientDC` 에 연결 된 개체는 `CWnd`합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CClientDC::m_hWnd](#m_hwnd)|`HWND` 이 대 한 창의 `CClientDC` 유효 합니다.|  
  
## <a name="remarks"></a>설명  
 즉, 연결 된 장치 컨텍스트는 `CClientDC` 개체는 창의 클라이언트 영역입니다.  
  
 대 한 자세한 내용은 `CClientDC`, 참조 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CClientDC`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cclientdc"></a>CClientDC::CClientDC  
 생성 된 `CClientDC` 의 클라이언트 영역에 액세스 하는 개체는 [CWnd](../../mfc/reference/cwnd-class.md) 가리키는 `pWnd`합니다.  
  
```  
explicit CClientDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 창 디바이스 컨텍스트 개체에 액세스할 클라이언트 영역입니다.  
  
### <a name="remarks"></a>설명  
 Windows 함수를 호출 하는 생성자 [GetDC](http://msdn.microsoft.com/library/windows/desktop/dd144871)합니다.  
  
 예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows `GetDC` 호출이 실패 합니다. 장치 컨텍스트에 Windows 이미 할당 된 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있는 수 있습니다. Windows에서 언제 든 지 사용할 수 있는 5 개의 일반적인 디스플레이 컨텍스트를 위한 응용 프로그램 완료 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>CClientDC::m_hWnd  
 `HWND` 의 `CWnd` 포인터 생성에 사용 되는 `CClientDC` 개체입니다.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>설명  
 `m_hWnd`보호 된 변수가입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CClientDC::CClientDC](#cclientdc)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)
