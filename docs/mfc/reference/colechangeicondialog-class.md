---
title: COleChangeIconDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::COleChangeIconDialog
- AFXODLGS/COleChangeIconDialog::DoChangeIcon
- AFXODLGS/COleChangeIconDialog::DoModal
- AFXODLGS/COleChangeIconDialog::GetIconicMetafile
- AFXODLGS/COleChangeIconDialog::m_ci
dev_langs:
- C++
helpviewer_keywords:
- COleChangeIconDialog [MFC], COleChangeIconDialog
- COleChangeIconDialog [MFC], DoChangeIcon
- COleChangeIconDialog [MFC], DoModal
- COleChangeIconDialog [MFC], GetIconicMetafile
- COleChangeIconDialog [MFC], m_ci
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40907720965647e076c6b516f1c2de9f1d3f9edb
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850568"
---
# <a name="colechangeicondialog-class"></a>COleChangeIconDialog 클래스
OLE 아이콘 변경 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeIconDialog::COleChangeIconDialog](#colechangeicondialog)|`COleChangeIconDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeIconDialog::DoChangeIcon](#dochangeicon)|대화 상자에서 지정한 변경을 수행 합니다.|  
|[COleChangeIconDialog::DoModal](#domodal)|OLE 2 아이콘 변경 대화 상자를 표시합니다.|  
|[COleChangeIconDialog::GetIconicMetafile](#geticonicmetafile)|이 항목의 아이콘을 폼에 연결 된 메타 파일에 대 한 핸들을 가져옵니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeIconDialog::m_ci](#m_ci)|대화 상자의 동작을 제어 하는 구조체입니다.|  
  
## <a name="remarks"></a>설명  
 클래스의 개체를 만들려면 `COleChangeIconDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COleChangeIconDialog` 생성 된 개체를 사용할 수 있습니다 합니다 [m_ci](#m_ci) 값 또는 대화 상자에서 컨트롤의 상태를 초기화 하는 구조입니다. `m_ci` OLEUICHANGEICON 형식의 구조입니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK에는 구조입니다.  
  
 OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="colechangeicondialog"></a>  COleChangeIconDialog::COleChangeIconDialog  
 이 함수가 구성만 `COleChangeIconDialog` 개체입니다.  
  
```  
explicit COleChangeIconDialog(
    COleClientItem* pItem,  
    DWORD dwFlags = CIF_SELECTCURRENT,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pItem*  
 변환할 항목을 가리킵니다.  
  
 *dwFlags*  
 원하는 수의 다음 값을 포함 하는 생성 플래그 비트를 사용 하 여 결합-or 연산자:  
  
- CIF_SELECTCURRENT 지정 현재 라디오 단추가 되도록 선택 대화 상자를 호출할 때. 이 값이 기본값입니다.  
  
- CIF_SELECTDEFAULT 지정 기본 라디오 단추 수 있는 선택 대화 상자를 호출할 때.  
  
- CIF_SELECTFROMFILE 지정 파일에서 라디오 단추 수 있는 선택 대화 상자를 호출할 때.  
  
- CIF_SHOWHELP는 도움말 단추가 대화 상자를 호출할 때 표시 되도록 지정 합니다.  
  
- CIF_USEICONEXE 아이콘을 추출 해야 하는에 지정 된 실행 파일에서 지정 된 `szIconExe` 필드 [m_ci](#m_ci) 대신 형식에서 검색 합니다. 이 포함 하거나 비 OLE 파일에 연결 하는 데 유용 합니다.  
  
 *pParentWnd*  
 부모 또는 소유자 창 개체 (형식의 `CWnd`) 대화 상자 개체 속한 합니다. NULL 인 경우 대화 상자의 부모 창 주 응용 프로그램 창에 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 표시 하려면 호출을 [DoModal](#domodal) 함수입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK에는 구조입니다.  
  
##  <a name="dochangeicon"></a>  COleChangeIconDialog::DoChangeIcon  
 한 후 대화 상자에서 선택한 항목을 나타내는 아이콘을 변경 하려면이 함수를 호출 [DoModal](#domodal) IDOK를 반환 합니다.  
  
```  
BOOL DoChangeIcon(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 *pItem*  
 해당 아이콘을 변경 하는 항목을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 변경에 성공 하면 0이 아닌 값 그렇지 않으면 0입니다.  
  
##  <a name="domodal"></a>  COleChangeIconDialog::DoModal  
 OLE 아이콘 변경 대화 상자를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- IDOK 대화 상자를 성공적으로 표시 된 경우입니다.  
  
- 사용자가 대화 상자를 취소 하는 경우 IDCANCEL 합니다.  
  
- IDABORT 오류가 발생 합니다. IDABORT 반환 되 면 호출 된 `COleDialog::GetLastError` 발생 한 오류 유형에 대 한 자세한 정보를 보려면 멤버 함수입니다. 목록을 가능한 오류에 대 한 참조를 [OleUIChangeIcon](http://msdn.microsoft.com/library/windows/desktop/ms688307) Windows SDK에는 함수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_ci](#m_ci) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체에서 생성 된 후 있지만.  
  
 경우 `DoModal` IDOK 반환 다른 멤버를 설정 또는 사용자가 대화 상자에 입력 된 정보를 검색 하는 함수를 호출할 수 있습니다.  
  
##  <a name="geticonicmetafile"></a>  COleChangeIconDialog::GetIconicMetafile  
 선택한 항목의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들을 가져오려면이 함수를 호출 합니다.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자를 선택 하 여 해제 된 경우 새 아이콘의 아이콘 모양을 포함 하는 메타 파일에 대 한 핸들 **확인**고, 그렇지 않으면 대화 상자가 표시 된 것으로 아이콘 전의 합니다.  
  
##  <a name="m_ci"></a>  COleChangeIconDialog::m_ci  
 OLEUICHANGEICON 형식의 구조 아이콘 변경 대화 상자의 동작을 제어 하는 데 사용 합니다.  
  
```  
OLEUICHANGEICON m_ci;  
```  
  
### <a name="remarks"></a>설명  
 이 구조체의 멤버는 직접 또는 멤버 함수를 통해 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) Windows SDK에는 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)
