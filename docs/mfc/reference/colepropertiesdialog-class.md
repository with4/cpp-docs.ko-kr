---
title: "COlePropertiesDialog 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::COlePropertiesDialog
- AFXODLGS/COlePropertiesDialog::DoModal
- AFXODLGS/COlePropertiesDialog::OnApplyScale
- AFXODLGS/COlePropertiesDialog::m_gp
- AFXODLGS/COlePropertiesDialog::m_lp
- AFXODLGS/COlePropertiesDialog::m_op
- AFXODLGS/COlePropertiesDialog::m_psh
- AFXODLGS/COlePropertiesDialog::m_vp
dev_langs:
- C++
helpviewer_keywords:
- COlePropertiesDialog [MFC], COlePropertiesDialog
- COlePropertiesDialog [MFC], DoModal
- COlePropertiesDialog [MFC], OnApplyScale
- COlePropertiesDialog [MFC], m_gp
- COlePropertiesDialog [MFC], m_lp
- COlePropertiesDialog [MFC], m_op
- COlePropertiesDialog [MFC], m_psh
- COlePropertiesDialog [MFC], m_vp
ms.assetid: a54dbc89-1447-4329-bd01-00e98ec9e935
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5460926e1f58a557b26d8e5fa0a0ed763fc5de6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="colepropertiesdialog-class"></a>COlePropertiesDialog 클래스
Windows 공용 OLE 개체 속성 대화 상자를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COlePropertiesDialog : public COleDialog  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COlePropertiesDialog::COlePropertiesDialog](#colepropertiesdialog)|`COlePropertiesDialog` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COlePropertiesDialog::DoModal](#domodal)|대화 상자를 표시 하 고 사용자는 선택할 수 있습니다.|  
|[COlePropertiesDialog::OnApplyScale](#onapplyscale)|문서 항목의 크기 조정을 변경 될 때 프레임 워크에서 호출 됩니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COlePropertiesDialog::m_gp](#m_gp)|"일반" 페이지를 초기화 하는 데 사용 되는 구조는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m_lp](#m_lp)|"링크" 페이지를 초기화 하는 데 사용 되는 구조는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m_op](#m_op)|초기화 하는 데 사용 되는 구조는 `COlePropertiesDialog` 개체입니다.|  
|[COlePropertiesDialog::m_psh](#m_psh)|추가 사용자 지정 속성 페이지를 추가 하는 데 사용 되는 구조입니다.|  
|[COlePropertiesDialog::m_vp](#m_vp)|"View" 페이지를 사용자 지정 하는 데 사용 되는 구조는 `COlePropertiesDialog` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 일반 OLE 개체 속성 대화 상자에는 쉽게 표시 하 고 Windows 표준와 일치 하는 방식에서 OLE 문서 항목의 속성을 수정 하는 방법을 제공 합니다. 이러한 속성 중 일부 옵션 (항목이 연결 된) 경우 항목의 링크에 아이콘 및 이미지 크기 조정 및 정보를 표시 하기 위한 문서 항목을 나타내는 파일에 대 한 정보가 들어 있습니다.  
  
 사용 하는 `COlePropertiesDialog` 개체를 사용 하 여 개체를 만들려면 먼저는 `COlePropertiesDialog` 생성자입니다. 대화 상자를 생성 한 후 호출 하 여 `DoModal` 대화 상자를 표시 하 고 사용자가 항목의 속성을 수정 하도록 허용 하려면 멤버 함수입니다. `DoModal`사용자는 확인 선택 여부를 반환 합니다 ( **IDOK**) 또는 Cancel ( **IDCANCEL**) 단추입니다. 확인 및 취소 단추 외에도 적용 단추가 있습니다. 사용자가 적용을 선택 하면 문서 항목의 속성을 변경한 항목에 적용 되 고 해당 이미지가 자동으로 업데이트 되었지만 활성 상태로 유지 됩니다.  
  
 [m_psh](#m_psh) 데이터 멤버에 대 한 포인터는 한 **PROPSHEETHEADER** 구조 및 대부분의 경우 명시적으로 액세스 해야 합니다. 기본 일반, 뷰 및 링크 페이지 이외의 추가 속성 페이지를 해야 하는 경우는 예외가입니다. 이 경우 수정할 수 있습니다는 `m_psh` 호출 하기 전에 사용자 지정 페이지를 포함 하도록 데이터 멤버는 `DoModal` 멤버 함수입니다.  
  
 OLE 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePropertiesDialog`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxodlgs.h  
  
##  <a name="colepropertiesdialog"></a>COlePropertiesDialog::COlePropertiesDialog  
 
          `COlePropertiesDialog` 개체를 만듭니다.  
  
```  
COlePropertiesDialog(
    COleClientItem* pItem,  
    UINT nScaleMin = 10,  
    UINT nScaleMax = 500,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 액세스 되는 속성을 가진 문서 항목에 대 한 포인터입니다.  
  
 *nScaleMin*  
 최소 배율 문서 항목 이미지에 대 한 백분율입니다.  
  
 *nScaleMax*  
 최대 조정 문서 항목 이미지에 대 한 백분율입니다.  
  
 `pParentWnd`  
 이 대화 상자의 부모 또는 소유자에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 일반 OLE 개체 속성 대화 상자 클래스에서 파생 `COlePropertiesDialog` 문서 항목에 대해 크기 조정을 구현 하는 데 있습니다. 이 클래스의 인스턴스에 의해 구현 된 모든 대화 상자에서 문서 항목의 크기 조정을 지원 하지 않습니다.  
  
 기본적으로 공용 OLE 개체 속성 대화 상자에는 세 가지 기본 페이지에 있습니다.  
  
-   일반  
  
     이 페이지는 선택한 문서 항목이 나타내는 파일에 대 한 시스템 정보를 포함 합니다. 이 페이지에서 사용자 다른 형식으로 선택한 항목 형식으로 변환할 수 있습니다.  
  
-   보기  
  
     이 페이지, 항목을 표시 하 고, 아이콘을 변경 하 고, 이미지의 크기를 변경 하는 옵션이 있습니다.  
  
-   링크  
  
     이 페이지에서 링크 된 항목의 위치를 변경 하 고 연결 된 항목을 업데이트 하는 옵션이 있습니다. 사용자는이 페이지에서 선택한 항목의 연결을 끊을 수 있습니다.  
  
 기본적으로 제공 하는 것 이상의 페이지에 추가 하려면 수정 된 [m_psh](#m_psh) 의 생성자를 종료 하기 전에 멤버 변수 프로그램 `COlePropertiesDialog`-클래스를 파생 합니다. 이의 고급 구현을 `COlePropertiesDialog` 생성자입니다.  
  
##  <a name="domodal"></a>COlePropertiesDialog::DoModal  
 Windows 공용 OLE 개체 속성 대화 상자를 표시 하 고 사용자가 보거나 문서 항목의 다양 한 속성을 변경 하도록 허용 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>반환 값  
 **IDOK** 또는 **IDCANCEL** 성공 하면 그렇지 않으면 0입니다. **IDOK** 및 **IDCANCEL** 는 사용자 확인 또는 취소 단추를 선택 하는지 여부를 나타내는 상수입니다.  
  
 경우 **IDCANCEL** 반환 되 면 Windows를 호출할 수 있습니다 [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) 함수 오류가 발생 한 것인지 확인 합니다.  
  
##  <a name="m_gp"></a>COlePropertiesDialog::m_gp  
 형식의 구조 [OLEUIGNRLPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687297), OLE 개체 속성 대화 상자의 일반 페이지를 초기화 하는 데 사용 합니다.  
  
```  
OLEUIGNRLPROPS m_gp;  
```  
  
### <a name="remarks"></a>설명  
 이 페이지는 유형 및 크기는 포함의 하며 변환 대화 상자에 대 한 사용자 액세스를 허용 합니다. 이 페이지에는 표시 링크 대상의 경우 개체는 링크입니다.  
  
 대 한 자세한 내용은 **OLEUIGNRLPROPS** 구조체는 Windows SDK를 참조 하십시오.  
  
##  <a name="m_lp"></a>COlePropertiesDialog::m_lp  
 형식의 구조 [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735), OLE 개체 속성 대화 상자의 연결 페이지를 초기화 하는 데 사용 합니다.  
  
```  
OLEUILINKPROPS m_lp;  
```  
  
### <a name="remarks"></a>설명  
 이 페이지는 링크 된 항목의 위치를 표시 및 사용 하면 업데이트 또는 중단 된 항목에 대 한 링크를 합니다.  
  
 대 한 자세한 내용은 **OLEUILINKPROPS** 구조체는 Windows SDK를 참조 하십시오.  
  
##  <a name="m_op"></a>COlePropertiesDialog::m_op  
 형식의 구조 [OLEUIOBJECTPROPS](http://msdn.microsoft.com/library/windows/desktop/ms687199), 공용 OLE 개체 속성 대화 상자를 초기화 하는 데 사용 합니다.  
  
```  
OLEUIOBJECTPROPS m_op;  
```  
  
### <a name="remarks"></a>설명  
 이 구조는 일반, 링크 및 보기 페이지를 초기화 하는 데 사용 되는 멤버를 포함 합니다.  
  
 자세한 내용은 참조는 **OLEUIOBJECTPROPS** 및 [OLEUILINKPROPS](http://msdn.microsoft.com/library/windows/desktop/ms680735) Windows SDK에는 구조입니다.  
  
##  <a name="m_psh"></a>COlePropertiesDialog::m_psh  
 형식의 구조 [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546), 멤버가 대화 상자 개체의 특성을 저장 합니다.  
  
```  
PROPSHEETHEADER m_psh;  
```  
  
### <a name="remarks"></a>설명  
 생성 한 후 한 `COlePropertiesDialog` 개체를 사용할 수 있습니다 `m_psh` 호출 하기 전에 대화 상자의 다양 한 측면을 설정 하는 `DoModal` 멤버 함수입니다.  
  
 수정 하는 경우는 `m_psh` 데이터 멤버를 직접 모든 기본 동작을 재정의 하 합니다.  
  
 대 한 자세한 내용은 **PROPSHEETHEADER** 구조체는 Windows SDK를 참조 하십시오.  
  
##  <a name="m_vp"></a>COlePropertiesDialog::m_vp  
 형식의 구조 [OLEUIVIEWPROPS](http://msdn.microsoft.com/library/windows/desktop/ms693751), OLE 개체 속성 대화 상자의 보기 페이지를 초기화 하는 데 사용 합니다.  
  
```  
OLEUIVIEWPROPS m_vp;  
```  
  
### <a name="remarks"></a>설명  
 이 페이지에서는 사용자를 "콘텐츠" 및 "아이콘" 뷰는 개체의 사이 전환 하 고 컨테이너 내에서 배율을 변경 합니다. 개체 아이콘으로 표시 되는 경우 아이콘 변경 대화 상자에 대 한 사용자 액세스를 수도 있습니다.  
  
 대 한 자세한 내용은 **OLEUIVIEWPROPS** 구조체는 Windows SDK를 참조 하십시오.  
  
##  <a name="onapplyscale"></a>COlePropertiesDialog::OnApplyScale  
 크기 조정 값 변경 되어 확인 또는 적용 중 하나를 선택한 경우 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnApplyScale(
    COleClientItem* pItem,  
    int nCurrentScale,  
    BOOL bRelativeToOrig);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 액세스 되는 속성을 가진 문서 항목에 대 한 포인터입니다.  
  
 `nCurrentScale`  
 대화 눈금의 숫자 값입니다.  
  
 *bRelativeToOrig*  
 문서 항목의 원래 크기에 배율을 적용 되는지 여부를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 처리 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 아무 작업도 수행하지 않습니다. 크기 조정 컨트롤을 사용 하려면이 함수를 재정의 해야 합니다.  
  
> [!NOTE]
>  프레임 워크에서이 함수를 호출 공용 OLE 개체 속성 대화 상자 표시 되기 전에 **NULL** 에 대 한 `pItem` 에-1 `nCurrentScale`합니다. 이 크기 조정 컨트롤을 사용 해야 하는지 확인 하려면 수행 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CIRC](../../visual-cpp-samples.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDialog 클래스](../../mfc/reference/coledialog-class.md)   
 [CPropertyPage 클래스](../../mfc/reference/cpropertypage-class.md)
