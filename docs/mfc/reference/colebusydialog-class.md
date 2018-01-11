---
title: "COleBusyDialog 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs: C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e57881dad305a5a0d5cec25ddcc93f82eca5f26
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="colebusydialog-class"></a>COleBusyDialog 클래스
OLE 서버가 응답하지 않음 또는 서버가 사용 중임 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|`COleBusyDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|OLE 서버 작업 중 대화 상자가 표시 됩니다.|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|대화 상자에서 선택한 옵션을 결정 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|형식의 구조 **OLEUIBUSY** 대화 상자의 동작을 제어 하는 합니다.|  
  
## <a name="remarks"></a>설명  
 클래스의 개체를 만들 `COleBusyDialog` 이러한 대화 상자를 호출 하려는 경우. 후는 `COleBusyDialog` 개체 생성 되었으며, 사용할 수 있습니다는 [m_bz](#m_bz) 구조를 값 이나 대화 상자에서 컨트롤의 상태를 초기화 합니다. `m_bz` 형식의 구조는 **OLEUIBUSY**합니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.  
  
> [!NOTE]
>  응용 프로그램 컨테이너 마법사에서 생성 된 코드는이 클래스를 사용합니다.  
  
 자세한 내용은 참조는 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK에는 구조입니다.  
  
 특정 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>COleBusyDialog::COleBusyDialog  
 이 함수가 구성 된 `COleBusyDialog` 개체입니다.  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *htaskBusy*  
 사용 중인 경우 서버 작업에 대 한 핸들입니다.  
  
 *bNotResponding*  
 경우 **TRUE**, 서버 작업 중 대화 상자 대신 응답 하지 않는 대화 상자를 호출 합니다. 서버 작업 중 대화 상자에서 표현을 보다 약간 다른 응답 하지 않는 대화 상자에서 표현을 이며 취소 단추가 비활성화 됩니다.  
  
 `dwFlags`  
 생성 플래그입니다. 0 개 이상의 비트 OR 연산자와 함께 다음 값을 포함할 수 있습니다.  
  
- **BZ_DISABLECANCELBUTTON** 대화 상자를 호출할 때 "취소" 단추가 사용 하지 않도록 설정 합니다.  
  
- **BZ_DISABLESWITCHTOBUTTON** 대화 상자를 호출 하는 경우 전환 단추를 사용 하지 않도록 설정 합니다.  
  
- **BZ_DISABLERETRYBUTTON** 대화 상자를 호출할 때 재시도 단추를 사용 하지 않도록 설정 합니다.  
  
 `pParentWnd`  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 상자 개체 속해 있는 합니다. 이 경우 **NULL**, 대화 상자 개체의 부모 창은 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 표시 하려면 호출 [DoModal](#domodal)합니다.  
  
 자세한 내용은 참조는 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK에는 구조입니다.  
  
##  <a name="domodal"></a>COleBusyDialog::DoModal  
 OLE 서버 작업 중 또는 서버가 응답 하지 않음 대화 상자를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자가 성공적으로 표시 된 경우.  
  
- **IDCANCEL** 대화 상자를 취소 합니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 `COleDialog::GetLastError` 형식 발생 한 오류에 대 한 자세한 정보를 보려면 멤버 함수입니다. 가능한 오류 목록을 참조 하십시오.는 [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) Windows SDK에는 함수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_bz](#m_bz) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 **IDOK**, 다른 멤버를 설정 또는 사용자가 대화 상자에 입력 된 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
##  <a name="getselectiontype"></a>COleBusyDialog::GetSelectionType  
 서버 작업 중 대화 상자에서 사용자가 선택한 선택 유형을 가져오려면이 함수를 호출 합니다.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목의 형식입니다.  
  
### <a name="remarks"></a>설명  
 반환 형식 값으로 지정 됩니다는 **선택** 열거형 형식에 선언 된는 `COleBusyDialog` 클래스입니다.  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 이러한 값에 대 한 간단한 설명을 따르십시오.  
  
- **COleBusyDialog::switchTo** 전환 단추를 눌렀습니다.  
  
- **COleBusyDialog::retry** 다시 시도 단추를 눌렀습니다.  
  
- **COleBusyDialog::callUnblocked** 호출 서버 정품 인증을 이제는 차단 해제 합니다.  
  
##  <a name="m_bz"></a>COleBusyDialog::m_bz  
 형식의 구조 **OLEUIBUSY** 서버 작업 중 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>설명  
 이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK에는 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)
