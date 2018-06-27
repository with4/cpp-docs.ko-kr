---
title: CDataExchange 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
dev_langs:
- C++
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed2f918a51c1dca1aa7e1713ac919102a599e38
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953349"
---
# <a name="cdataexchange-class"></a>CDataExchange 클래스
Microsoft Foundation 클래스에서 사용되는 DDX(대화 상자 데이터 교환) 및 DDV(대화 상자 데이터 유효성 검사) 루틴을 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDataExchange  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDataExchange::CDataExchange](#cdataexchange)|`CDataExchange` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|유효성 검사가 실패할 때 호출 됩니다. 이전 컨트롤로 포커스를 다시 설정 하 고 예외를 throw 합니다.|  
|[CDataExchange::PrepareCtrl](#preparectrl)|데이터 교환 또는 유효성 검사에 대 한 지정된 된 컨트롤을 준비합니다. Nonedit 컨트롤에 사용 됩니다.|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|데이터 교환 또는 유효성 검사에 대 한 지정 된 편집 컨트롤을 준비합니다.|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|데이터 교환 또는 유효성 검사에 대 한 지정된 된 OLE 컨트롤을 준비합니다. Nonedit 컨트롤에 사용 됩니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX 및 DDV의 방향에 대 한 플래그입니다.|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|데이터를 교환할 대화 상자 또는 창에 수행이 됩니다.|  
  
## <a name="remarks"></a>설명  
 `CDataExchange` 기본 클래스는 없습니다.  
  
 사용자 지정 데이터 형식이 나 컨트롤에 대 한 데이터 교환 루틴을 작성 하는 경우에이 클래스를 사용 하 여 사용자 고유의 데이터 유효성 검사 루틴을 작성 하는 경우 또는 합니다. 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자](../../mfc/dialog-boxes.md)합니다.  
  
 A `CDataExchange` 개체에 배치 되려면 DDX 및 DDV 필요한 컨텍스트 정보를 제공 합니다. 플래그 *m_bSaveAndValidate* 은 **FALSE** DDX 데이터 멤버에서 대화 상자 컨트롤의 초기 값을 채우는 데 사용 되는 경우. 플래그 *m_bSaveAndValidate* 은 **TRUE** 데이터 멤버 및 DDV 데이터 값의 유효성 검사에 사용 되는 경우에 대화 상자 컨트롤의 현재 값을 설정 하려면 DDX 사용 되는 경우. DDV 유효성 검사에 실패 하는 경우 입력된 오류를 설명 하는 메시지 상자 DDV 절차에 표시 됩니다. 그런 다음 DDV 프로시저가 호출 `Fail` 문제가 되는 컨트롤에 포커스를 다시 설정 하 고 유효성 검사 프로세스를 중지 하려면 예외를 throw 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CDataExchange`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange  
 생성 하려면이 멤버 함수 호출을 `CDataExchange` 개체입니다.  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDlgWnd*  
 컨트롤이 포함 된 부모 창에 대 한 포인터입니다. 이 일반적으로 [CDialog](../../mfc/reference/cdialog-class.md)-파생 된 개체입니다.  
  
 *bSaveAndValidate*  
 경우 **TRUE**,이 개체 데이터의 유효성을 검사 한 다음 멤버를 컨트롤에서 데이터를 씁니다. 경우 **FALSE**,이 개체 멤버에서 컨트롤에 데이터를 이동 합니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CDataExchange` 개체 창의에 전달할 데이터 교환 개체에 추가 정보를 저장 하기 위해 직접 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>  CDataExchange::Fail  
 프레임 워크 대화 상자 데이터 유효성 검사 (DDV) 작업이 실패 하면이 멤버 함수를 호출 합니다.  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>설명  
 `Fail` 포커스 및 선택 (있는 경우 복원 하는 컨트롤)를 유효성 검사에 실패 하는 컨트롤에 복원 합니다. `Fail` 다음 형식의 예외를 throw [CUserException](../../mfc/reference/cuserexception-class.md) 유효성 검사 프로세스를 중지 합니다. 예외 하면 표시할 오류를 설명 하는 메시지 상자. DDV 유효성 검사에 실패 한 후 사용자를 문제가 되는 컨트롤의 데이터를 다시 입력할 수 있습니다.  
  
 사용자 지정 DDV 루틴의 구현자를 호출할 수 `Fail` 유효성 검사가 실패할 때 자신의 루틴에서 합니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate  
 이 플래그는 대화 상자 데이터 교환 (DDX) 작업의 방향을 나타냅니다.  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>설명  
 플래그는 0이 아닌 경우는 `CDataExchange` 개체가 사용 되는 사용자가 컨트롤을 편집 후 대화 상자 클래스 데이터 멤버 대화 상자 컨트롤에서 데이터 이동 합니다. 대화 상자 클래스 데이터 멤버에서 대화 상자 컨트롤을 초기화 하는 개체가 사용 되는 경우 0은 있습니다.  
  
 플래그 대화 상자 데이터 유효성 검사 (DDV) 하는 동안 0이 아닌 이기도합니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 어떤 대화에 대 한 DDX 데이터 교환 () 또는 유효성 검사 (DDV) 수행 되는 개체입니다.  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>설명  
 이 개체는 일반적으로 [CDialog](../../mfc/reference/cdialog-class.md) 개체입니다. 사용자 지정 DDX 또는 DDV 루틴의 구현자가이 포인터를 사용에 적용 될 컨트롤을 포함 하는 대화 상자 창에 대 한 액세스를 가져올 수 있습니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl  
 프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정된 된 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>매개 변수  
 *nIDC*  
 DDX 또는 DDV가 준비 될 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `HWND` DDX 또는 DDV가 준비 되 고 컨트롤의 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [PrepareEditCtrl](#prepareeditctrl) 대신; 편집 컨트롤에 대 한 다른 모든 컨트롤에 대 한이 멤버 함수를 사용 합니다.  
  
 준비 저장 컨트롤의 이루어져 `HWND` 에 `CDataExchange` 클래스입니다. 프레임 워크 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 있는 컨트롤에 포커스를 복원 하려면이 핸들을 사용 합니다.  
  
 사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareCtrl` 모든 비 편집 컨트롤을 DDX 통해 데이터를 교환 인지 DDV 통해 데이터 유효성 검사에 대 한 합니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl  
 프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정 된 편집 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>매개 변수  
 *nIDC*  
 DDX 또는 DDV가 준비 될 편집 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 `HWND` DDX 또는 DDV가 준비 되 고 편집 컨트롤의 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [PrepareCtrl](#preparectrl) 대신 모든 비 편집 컨트롤에 대 한 합니다.  
  
 다음 두 가지 중 준비 구성 됩니다. 첫째, `PrepareEditCtrl` 컨트롤의 저장 `HWND` 에 `CDataExchange` 클래스입니다. 프레임 워크 DDX 또는 DDV 오류가 발생할 경우 이전에 포커스가 있는 컨트롤에 포커스를 복원 하려면이 핸들을 사용 합니다. 두 번째, `PrepareEditCtrl` 에 플래그를 설정의 `CDataExchange` 을 나타내는 클래스 해당 데이터가 교환 중인 또는 유효성을 검사 하는 것은 편집 컨트롤 컨트롤입니다.  
  
 사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareEditCtrl` 모든 편집 컨트롤을 DDX 통해 데이터를 교환 인지 DDV 통해 데이터 유효성 검사에 대 한 합니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl  
 프레임 워크 (DDX) 대화 상자 데이터 교환 및 유효성 검사 (DDV)에 지정된 된 OLE 컨트롤을 준비 하려면이 멤버 함수를 호출 합니다.  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>매개 변수  
 *nIDC*  
 DDX 또는 DDV가 준비 될 OLE 컨트롤의 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 OLE 컨트롤 사이트에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [PrepareEditCtrl](#prepareeditctrl) 대신 편집 컨트롤에 대 한 또는 [PrepareCtrl](#preparectrl) 다른 모든 비 OLE 컨트롤에 대 한 합니다.  
  
 사용자 지정 DDX 또는 DDV 루틴의 구현자를 호출 해야 `PrepareOleCtrl` 모든 OLE 컨트롤을 DDX 통해 데이터를 교환 인지 DDV 통해 데이터 유효성 검사에 대 한 합니다.  
  
 사용자 고유의 DDX 및 DDV 루틴을 작성 방법에 대 한 자세한 내용은 참조 하십시오. [기술 참고 26](../../mfc/tn026-ddx-and-ddv-routines.md)합니다. DDX 및 DDV의 개요를 참조 하십시오. [대화 상자 데이터 교환 및 유효성 검사](../../mfc/dialog-data-exchange-and-validation.md) 및 [대화 상자 항목](../../mfc/dialog-boxes.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 VIEWEX](../../visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

