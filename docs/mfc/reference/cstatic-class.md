---
title: CStatic 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
dev_langs:
- C++
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d3b1a5dcfc8481727bffd8b80e0bb1b230d56ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375006"
---
# <a name="cstatic-class"></a>CStatic 클래스
Windows 정적 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CStatic : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CStatic::CStatic](#cstatic)|`CStatic` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStatic::Create](#create)|Windows 정적 컨트롤을 만들고에 연결 된 `CStatic` 개체입니다.|  
|[CStatic::DrawItem](#drawitem)|소유자가 그린 정적 컨트롤 그리기를 재정의 합니다.|  
|[CStatic::GetBitmap](#getbitmap)|이전에 사용 하 여 설정 하는 비트맵의 핸들을 검색 [SetBitmap](#setbitmap)합니다.|  
|[CStatic::GetCursor](#getcursor)|검색으로 이전에 설정 된 커서 이미지 핸들 [SetCursor](#setcursor)합니다.|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|이전에 설정 된 확장된 메타 파일의 핸들을 검색 [SetEnhMetaFile](#setenhmetafile)합니다.|  
|[CStatic::GetIcon](#geticon)|이전에 사용 하 여 설정 아이콘의 핸들을 검색 [SetIcon](#seticon)합니다.|  
|[CStatic::SetBitmap](#setbitmap)|정적 컨트롤에 표시할 비트맵을 지정 합니다.|  
|[CStatic::SetCursor](#setcursor)|정적 컨트롤에 표시할 커서 이미지를 지정 합니다.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|정적 컨트롤에 표시할 확장된 메타 파일을 지정 합니다.|  
|[CStatic::SetIcon](#seticon)|정적 컨트롤에 표시할 아이콘을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 정적 컨트롤 텍스트 문자열, 상자, 사각형, 아이콘, 커서, 비트맵 또는 메타 파일을 표시합니다. 레이블, 상자 또는 다른 컨트롤에 구분에 사용할 수 있습니다. 정적 컨트롤을 일반적으로 없는 입력을 제공 출력이 없습니다. 그러나로 생성 하는 경우 해당 부모 마우스 클릭 알릴 수 것 **SS_NOTIFY** 스타일입니다.  
  
 두 단계에서 정적 컨트롤을 만듭니다. 먼저,을 만드는 생성자를 호출는 `CStatic` 개체를 호출 합니다는 [만들기](#create) 정적 컨트롤을 만들고에 연결 하는 멤버 함수는 `CStatic` 개체입니다.  
  
 만드는 경우는 `CStatic` (대화 상자 리소스의 경우) 하 여 대화 상자 내에서 개체는 `CStatic` 개체는 사용자가 대화 상자를 닫을 때 자동으로 제거 됩니다.  
  
 만드는 경우는 `CStatic` 개체 창으로 삭제 해야 할 수도 있습니다. A `CStatic` 스택 창 내에서 만든 개체에 자동으로 제거 됩니다. 만들면는 `CStatic` 개체를 사용 하 여 힙에 **새** 함수를 호출한 다음 **삭제** 완료 되 면 파기 개체에 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="create"></a>  CStatic::Create  
 Windows 정적 컨트롤을 만들고에 연결 된 `CStatic` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszText,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID = 0xffff);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszText`  
 컨트롤에 배치할 텍스트를 지정 합니다. 경우 **NULL**, 텍스트가 표시 됩니다.  
  
 `dwStyle`  
 정적 컨트롤의 창 스타일을 지정합니다. 어떠한 조합의 적용 [정적 컨트롤 스타일](../../mfc/reference/styles-used-by-mfc.md#static-styles) 컨트롤에 있습니다.  
  
 `rect`  
 정적 컨트롤의 크기와 위치를 지정합니다. 있습니다는 `RECT` 구조 또는 `CRect` 개체입니다.  
  
 `pParentWnd`  
 지정 된 `CStatic` 부모 창, 일반적으로 `CDialog` 개체입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 정적 컨트롤의 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 된 `CStatic` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 합니다. `CStatic`, 한 다음 호출 **만들기**, Windows 정적 컨트롤을 만들고에 연결 하는 `CStatic` 개체입니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 정적 컨트롤에:  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** Usually  
  
- **WS_DISABLED** 거의  
  
 다음 중 하나를 적용 해야 정적 컨트롤에 비트맵, 커서, 아이콘 또는 메타 파일을 표시 하려는 경우 [정적 스타일](../../mfc/reference/styles-used-by-mfc.md#static-styles):  
  
- **SS_BITMAP** 비트맵에 대 한이 스타일을 사용 합니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 사용 합니다.  
  
- **SS_ENHMETAFILE** 향상 된 메타 파일에 대 한이 스타일을 사용 합니다.  
  
 커서, 비트맵 또는 아이콘을 다음 스타일을 사용 하 여 할 수도 있습니다.  
  
- **SS_CENTERIMAGE** 가운데 맞춤 정적 컨트롤의 이미지를 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>  CStatic::CStatic  
 `CStatic` 개체를 생성합니다.  
  
```  
CStatic();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>  CStatic::DrawItem  
 소유자가 그린 정적 컨트롤 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) 구조입니다. 구조에 필요한 그리기의 형식과 항목을 그릴 수 있도록 하는 방법에 대 한 정보가 들어 있습니다.  
  
### <a name="remarks"></a>설명  
 소유자가 그린에 대 한 그리기를 구현 하려면이 함수를 재정의 **CStatic** 개체 (컨트롤에 스타일이 **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>  CStatic::GetBitmap  
 이전에 사용 하 여 설정 하는 비트맵의 핸들을 가져옵니다 [SetBitmap](#setbitmap), 즉 연관 `CStatic`합니다.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 비트맵에 대 한 핸들 또는 **NULL** 비트맵이 없습니다 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>  CStatic::GetCursor  
 이전에 설정 된 커서의 핸들을 가져옵니다 [SetCursor](#setcursor), 즉 연관 `CStatic`합니다.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>반환 값  
 현재 커서에 대 한 핸들 또는 **NULL** 커서가 없습니다 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile  
 이전에 설정 된 확장된 메타 파일의 핸들을 가져옵니다 [SetEnhMetafile](#setenhmetafile), 즉 연관 `CStatic`합니다.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 확장된 메타 파일에 대 한 핸들 또는 **NULL** 없는 확장된 메타 파일 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>  CStatic::GetIcon  
 이전에 사용 하 여 설정 아이콘의 핸들을 가져옵니다 [SetIcon](#seticon), 즉 연관 `CStatic`합니다.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 아이콘에 대 한 핸들 또는 **NULL** 아이콘이 없는 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>  CStatic::SetBitmap  
 새 비트맵을 정적 컨트롤에 연결합니다.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `hBitmap`  
 정적 컨트롤에 그릴 비트맵의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 정적 컨트롤에 연결 되었던으로 비트맵의 핸들 또는 `NULL` 비트맵이 없습니다 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>설명  
 비트맵 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 놓입니다 하 고 비트맵의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 정적 컨트롤 스타일,이 포함 하 여 사용할 수 있습니다.  
  
-   SS_BITMAP은 비트맵에 대 한이 스타일을 항상 사용 합니다.  
  
-   정적 컨트롤의 이미지를 중앙 SS_CENTERIMAGE 사용 합니다. 이미지는 정적 컨트롤 보다 클 경우 잘립니다. 정적 컨트롤 보다 작은 경우 이미지 주위의 빈 공간으로 비트맵의 왼쪽된 위 모퉁이 있는 픽셀의 색으로 채워집니다.  
  
-   클래스를 제공 하는 MFC `CBitmap`, 수행 더 Win32 호출 보다 비트맵 이미지와 함께 작동 하는 경우 사용할 수 있는 `LoadBitmap`합니다. `CBitmap`를 한 종류의 GDI 개체를 포함 하는 대개 협력 하 여 `CStatic`,이 `CWnd` 정적 컨트롤 그래픽 개체를 표시 하는 중에 사용 되는 클래스입니다.  
  
 `CImage` 더 많은 장치 독립적 비트맵 DIB ()을 쉽게 작업할 수 있도록 ATL/MFC 클래스가입니다. 자세한 내용은 참조 [CImage 클래스](../../atl-mfc-shared/reference/cimage-class.md)합니다.  
  
-   지정 하는 일반적인 사용 `CStatic::SetBitmap` HBITMAP 운영자에 의해 반환 되는 GDI 개체는 `CBitmap` 또는 `CImage` 개체입니다. 이 작업을 수행 하는 코드에 다음 줄와 유사 합니다.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
다음 예제에서는 두 개의 `CStatic` 힙의 개체입니다. 다음을 사용 하 여 시스템 비트맵 로드 `CBitmap::LoadOEMBitmap` 및 사용 하 여 파일에서 다른 `CImage::Load`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>  CStatic::SetCursor  
 새 커서 이미지 정적 컨트롤에 연결합니다.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>매개 변수  
 `hCursor`  
 정적 컨트롤에 그릴 커서의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 정적 컨트롤을 이전에 연관 된 커서의 핸들 또는 **NULL** 커서가 없습니다 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>설명  
 커서는 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 놓입니다 하 고는 커서의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 정적 컨트롤 스타일을 포함 하 여 다음을 사용할 수 있습니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 항상 사용 합니다.  
  
- **SS_CENTERIMAGE** 가운데 맞춤 정적 컨트롤을 사용 합니다. 이미지는 정적 컨트롤 보다 클 경우 잘립니다. 정적 컨트롤 보다 작은 경우 이미지 주위의 빈 공간을 정적 컨트롤의 배경색으로 입력 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile  
 정적 컨트롤을 새 확장된 메타 파일 이미지를 연결합니다.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMetaFile`  
 정적 컨트롤에 그릴 확장된 메타 파일의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 정적 컨트롤과 연결 된 확장된 메타 파일의 핸들 또는 **NULL** 없는 확장된 메타 파일 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>설명  
 확장된 메타 파일 정적 컨트롤에 자동으로 그려집니다. 확장된 메타 파일 정적 컨트롤의 크기에 맞게 크기가 조정 됩니다.  
  
 다양 한 창 및 정적 컨트롤 스타일을 포함 하 여 다음을 사용할 수 있습니다.  
  
- **SS_ENHMETAFILE** 향상 된 메타 파일에 대 한이 스타일을 항상 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>  CStatic::SetIcon  
 새 아이콘 이미지를 정적 컨트롤에 연결합니다.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 `hIcon`  
 정적 컨트롤에 그릴 아이콘의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 정적 컨트롤을 이전에 연관 된 아이콘의 핸들 또는 **NULL** 아이콘이 없는 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>설명  
 아이콘 정적 컨트롤에 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 놓입니다 하 고 아이콘의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 정적 컨트롤 스타일을 포함 하 여 다음을 사용할 수 있습니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 항상 사용 합니다.  
  
- **SS_CENTERIMAGE** 가운데 맞춤 정적 컨트롤을 사용 합니다. 이미지는 정적 컨트롤 보다 클 경우 잘립니다. 정적 컨트롤 보다 작은 경우 이미지 주위의 빈 공간을 정적 컨트롤의 배경색으로 입력 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)   
 [CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)
