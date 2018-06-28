---
title: COleChangeSourceDialog 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::COleChangeSourceDialog
- AFXODLGS/COleChangeSourceDialog::DoModal
- AFXODLGS/COleChangeSourceDialog::GetDisplayName
- AFXODLGS/COleChangeSourceDialog::GetFileName
- AFXODLGS/COleChangeSourceDialog::GetFromPrefix
- AFXODLGS/COleChangeSourceDialog::GetItemName
- AFXODLGS/COleChangeSourceDialog::GetToPrefix
- AFXODLGS/COleChangeSourceDialog::IsValidSource
- AFXODLGS/COleChangeSourceDialog::m_cs
dev_langs:
- C++
helpviewer_keywords:
- COleChangeSourceDialog [MFC], COleChangeSourceDialog
- COleChangeSourceDialog [MFC], DoModal
- COleChangeSourceDialog [MFC], GetDisplayName
- COleChangeSourceDialog [MFC], GetFileName
- COleChangeSourceDialog [MFC], GetFromPrefix
- COleChangeSourceDialog [MFC], GetItemName
- COleChangeSourceDialog [MFC], GetToPrefix
- COleChangeSourceDialog [MFC], IsValidSource
- COleChangeSourceDialog [MFC], m_cs
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08b4095b535724f7132a2b286ce52cb46286932b
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037598"
---
# <a name="colechangesourcedialog-class"></a>COleChangeSourceDialog 클래스
OLE 소스 변경 대화 상자에 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](#colechangesourcedialog)|`COleChangeSourceDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeSourceDialog::DoModal](#domodal)|OLE 소스 변경 대화 상자를 표시합니다.|  
|[COleChangeSourceDialog::GetDisplayName](#getdisplayname)|전체 소스 표시 이름을 가져옵니다.|  
|[COleChangeSourceDialog::GetFileName](#getfilename)|원본 이름에서 파일 이름을 가져옵니다.|  
|[COleChangeSourceDialog::GetFromPrefix](#getfromprefix)|이전 소스 접두사를 가져옵니다.|  
|[COleChangeSourceDialog::GetItemName](#getitemname)|원본 이름에서 항목 이름을 가져옵니다.|  
|[COleChangeSourceDialog::GetToPrefix](#gettoprefix)|새 원본의 접두사를 가져옵니다.|  
|[COleChangeSourceDialog::IsValidSource](#isvalidsource)|소스가 유효한 나타냅니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleChangeSourceDialog::m_cs](#m_cs)|대화 상자의 동작을 제어 하는 구조입니다.|  
  
## <a name="remarks"></a>설명  
 클래스의 개체를 만들 `COleChangeSourceDialog` 이 대화 상자를 호출 하려는 경우. 후는 `COleChangeSourceDialog` 개체 생성 되었으며, 사용할 수 있습니다는 [m_cs](#m_cs) 구조를 값 이나 대화 상자에서 컨트롤의 상태를 초기화 합니다. `m_cs` 형식의 구조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)합니다. 이 대화 상자 클래스를 사용 하는 방법에 대 한 자세한 내용은 참조는 [DoModal](#domodal) 멤버 함수입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK에는 구조입니다.  
  
 특정 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="colechangesourcedialog"></a>  COleChangeSourceDialog::COleChangeSourceDialog  
 이 함수를 생성 한 `COleChangeSourceDialog` 개체입니다.  
  
```  
explicit COleChangeSourceDialog(
    COleClientItem* pItem,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pItem*  
 연결에 대 한 포인터 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 원본이 업데이트 해야 합니다.  
  
 *pParentWnd*  
 부모 또는 소유자 창 개체를 가리키는 (형식의 `CWnd`) 대화 상자 개체 속해 있는 합니다. 이 경우 **NULL**, 대화 상자의 부모 창 주 응용 프로그램 창으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 대화 상자를 표시 하려면 호출는 [DoModal](#domodal) 함수입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) 구조 및 [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK의 함수입니다.  
  
##  <a name="domodal"></a>  COleChangeSourceDialog::DoModal  
 OLE 소스 변경 대화 상자를 표시 하려면이 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자에 대 한 완료 상태입니다. 다음 값 중 하나입니다.  
  
- **IDOK** 대화 상자가 성공적으로 표시 된 경우.  
  
- **IDCANCEL** 대화 상자를 취소 합니다.  
  
- **IDABORT** 오류가 발생 합니다. 경우 **IDABORT** 은 호출 반환 되는 [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) 형식 발생 한 오류에 대 한 자세한 정보를 보려면 멤버 함수입니다. 가능한 오류 목록을 참조 하십시오.는 [OleUIChangeSource](http://msdn.microsoft.com/library/windows/desktop/ms682497) Windows SDK의 함수입니다.  
  
### <a name="remarks"></a>설명  
 멤버를 설정 하 여 다양 한 대화 상자 컨트롤을 초기화 하려는 경우는 [m_cs](#m_cs) 구조를 호출 하기 전에이 작업을 수행 해야 `DoModal`, 대화 상자 개체를 생성 한 후 하지만 합니다.  
  
 경우 `DoModal` 반환 **IDOK**, 대화 상자에서 사용자가 입력 한 설정이 나 정보를 검색 하는 함수 멤버를 호출할 수 있습니다. 다음 목록에서는 일반적인 쿼리 함수를 가지:  
  
- [GetFileName](#getfilename)  
  
- [GetDisplayName](#getdisplayname)  
  
- [GetItemName](#getitemname)  
  
##  <a name="getdisplayname"></a>  COleChangeSourceDialog::GetDisplayName  
 연결 된 클라이언트 항목에 대 한 전체 표시 이름을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetDisplayName();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 전체 원본 표시 이름 (모니커)는 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 생성자에 지정 합니다.  
  
##  <a name="getfilename"></a>  COleChangeSourceDialog::GetFileName  
 연결 된 클라이언트 항목에 대 한 표시 이름의 파일 모니커 부분을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetFileName();
```  
  
### <a name="return-value"></a>반환 값  
 원본 표시 이름에 대 한 파일 모니커 부분은 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 생성자에 지정 합니다.  
  
### <a name="remarks"></a>설명  
 항목 모니커 함께 파일 모니커 전체 표시 이름을 제공합니다.  
  
##  <a name="getfromprefix"></a>  COleChangeSourceDialog::GetFromPrefix  
 원본에 대 한 이전 접두사 문자열을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetFromPrefix();
```  
  
### <a name="return-value"></a>반환 값  
 소스의 이전 접두사 문자열입니다.  
  
### <a name="remarks"></a>설명  
 호출 후에이 기능 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 이 값에서 직접 가져온는 **lpszFrom** 의 멤버는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) 구조입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK에는 구조입니다.  
  
##  <a name="getitemname"></a>  COleChangeSourceDialog::GetItemName  
 연결 된 클라이언트 항목에 대 한 표시 이름의 항목 모니커 부분을 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetItemName();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 원본 표시 이름 항목 모니커 부분은 [COleClientItem](../../mfc/reference/coleclientitem-class.md) 생성자에 지정 합니다.  
  
### <a name="remarks"></a>설명  
 항목 모니커 함께 파일 모니커 전체 표시 이름을 제공합니다.  
  
##  <a name="gettoprefix"></a>  COleChangeSourceDialog::GetToPrefix  
 원본에 대 한 새 접두사 문자열을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetToPrefix();
```  
  
### <a name="return-value"></a>반환 값  
 원본의 새 접두사 문자열입니다.  
  
### <a name="remarks"></a>설명  
 호출 후에이 기능 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 이 값에서 직접 가져온는 **lpszTo** 의 멤버는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) 구조입니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK에는 구조입니다.  
  
##  <a name="m_cs"></a>  COleChangeSourceDialog::m_cs  
 이 데이터 멤버는 형식의 구조 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160)합니다.  
  
```  
OLEUICHANGESOURCE m_cs;  
```  
  
### <a name="remarks"></a>설명  
 `OLEUICHANGESOURCE` OLE 소스 변경 대화 상자의 동작을 제어 하는 데 사용 됩니다. 이 구조체의 멤버는 직접 수정할 수 있습니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK에는 구조입니다.  
  
##  <a name="isvalidsource"></a>  COleChangeSourceDialog::IsValidSource  
 새 소스 유효한 지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL IsValidSource();
```  
  
### <a name="return-value"></a>반환 값  
 새 소스가 유효한, 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출 후에이 기능 [DoModal](#domodal) 반환 **IDOK**합니다.  
  
 자세한 내용은 참조는 [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) Windows SDK에는 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)
