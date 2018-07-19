---
title: CWindowDC 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
dev_langs:
- C++
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b757da27f2b4ae79a0192df0598f833b3d1e7b9
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121544"
---
# <a name="cwindowdc-class"></a>CWindowDC 클래스
`CDC`에서 파생됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWindowDC : public CDC  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWindowDC::CWindowDC](#cwindowdc)|`CWindowDC` 개체를 생성합니다.|  
  
### <a name="protected-data-members"></a>보호된 데이터 멤버  
  
|name|설명|  
|----------|-----------------|  
|[CWindowDC::m_hWnd](#m_hwnd)|이 HWND `CWindowDC` 연결 됩니다.|  
  
## <a name="remarks"></a>설명  
 Windows 함수 호출 [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947\(v=vs.85\).aspx)생성 시 및 [ReleaseDC](http://msdn.microsoft.com/library/windows/desktop/dd162920\(v=vs.85\).aspx) 소멸 시. 즉, 한 `CWindowDC` 개체의 전체 화면 영역에 액세스 하는 [CWnd](../../mfc/reference/cwnd-class.md) (클라이언트 및 비클라이언트 영역).  
  
 사용 하 여 대 한 자세한 내용은 `CWindowDC`, 참조 [장치 컨텍스트](../../mfc/device-contexts.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CWindowDC`  
  
## <a name="requirements"></a>요구 사항  
 헤더: afxwin.h  
  
##  <a name="cwindowdc"></a>  CWindowDC::CWindowDC  
 생성 된 `CWindowDC` 의 전체 화면 영역 (클라이언트 및 비클라이언트)에 액세스 하는 개체는 `CWnd` 가리키는 개체 *pWnd*합니다.  
  
```  
explicit CWindowDC(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 창 디바이스 컨텍스트 개체에 액세스할 클라이언트 영역입니다.  
  
### <a name="remarks"></a>설명  
 Windows 함수를 호출 하는 생성자 [GetWindowDC](http://msdn.microsoft.com/library/windows/desktop/dd144947)합니다.  
  
 예외 (형식의 `CResourceException`) 하는 경우 throw 되는 Windows `GetWindowDC` 호출이 실패 합니다. 장치 컨텍스트에 Windows 이미 할당 된 모든 사용 가능한 장치 컨텍스트에서 사용할 수 있는 수 있습니다. Windows에서 언제 든 지 사용할 수 있는 5 개의 일반적인 디스플레이 컨텍스트를 위한 응용 프로그램 완료 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]  
  
##  <a name="m_hwnd"></a>  CWindowDC::m_hWnd  
 HWND는 `CWnd` 포인터를 사용 하 여 생성에 `CWindowDC` 개체입니다.  
  
```  
HWND m_hWnd;  
```  
  
### <a name="remarks"></a>설명  
 `m_hWnd` 보호 된 HWND 형식의 변수가입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CWindowDC::CWindowDC](#cwindowdc)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CDC 클래스](../../mfc/reference/cdc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)
