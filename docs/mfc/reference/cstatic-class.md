---
title: "CStatic 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- enhanced metafiles
- cursors, displaying
- static controls
- controls [MFC], static
- icons, displaying
- CStatic class
- enhanced metafiles, displaying
- bitmaps, displaying
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0209fad1b84b782cdec7927cb5a04e9bb3083d64
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CStatic::Create](#create)|Windows 정적 컨트롤을 만들고 연결 하는 `CStatic` 개체입니다.|  
|[CStatic::DrawItem](#drawitem)|소유자가 그린 정적 컨트롤 그리기를 재정의 합니다.|  
|[CStatic::GetBitmap](#getbitmap)|이전에 설정 된 비트맵의 핸들을 검색 [SetBitmap](#setbitmap)합니다.|  
|[CStatic::GetCursor](#getcursor)|검색으로 이전에 설정 된 커서 이미지의 핸들 [SetCursor](#setcursor)합니다.|  
|[CStatic::GetEnhMetaFile](#getenhmetafile)|이전에 설정 된 확장된 메타 파일의 핸들을 검색 [SetEnhMetaFile](#setenhmetafile)합니다.|  
|[CStatic::GetIcon](#geticon)|이전에 설정 된 아이콘의 핸들을 검색 [SetIcon](#seticon)합니다.|  
|[CStatic::SetBitmap](#setbitmap)|정적 컨트롤에 표시 되는 비트맵을 지정 합니다.|  
|[CStatic::SetCursor](#setcursor)|정적 컨트롤에 표시할 커서 이미지를 지정 합니다.|  
|[CStatic::SetEnhMetaFile](#setenhmetafile)|정적 컨트롤에 표시 되는 확장된 메타 파일을 지정 합니다.|  
|[CStatic::SetIcon](#seticon)|정적 컨트롤에 표시할 아이콘을 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 정적 컨트롤 텍스트 문자열, 상자, 사각형, 아이콘, 커서, 비트맵 또는 확장된 메타 파일을 표시합니다. 레이블, 상자 또는 다른 컨트롤을 별도 사용할 수 있습니다. 정적 컨트롤에서 일반적으로 입력 하지 않고 하 고 제공 출력이 없습니다. 그러나 그에 알릴 수의 마우스 클릭 만으로 부모로 만들어 **SS_NOTIFY** 스타일입니다.  
  
 2 단계를 거쳐에서 정적 컨트롤을 만듭니다. 먼저,을 만드는 생성자를 호출는 `CStatic` 개체를 만든 다음 호출에서 [만들기](#create) 정적 컨트롤을 만들고에 연결 하는 멤버 함수는 `CStatic` 개체입니다.  
  
 만드는 경우는 `CStatic` (대화 상자 리소스의 경우)를 통해 대화 상자 내에서 개체는 `CStatic` 개체는 사용자가 대화 상자를 닫을 때 자동으로 삭제 됩니다.  
  
 만드는 경우는 `CStatic` 창으로 개체를 파기 해야 할 수도 있습니다. A `CStatic` 스택 창 내에서 만든 개체를 자동으로 삭제 됩니다. 만드는 경우는 `CStatic` 개체를 사용 하 여 힙에 **새** 호출 해야 함수를 **삭제** 완료 되 면 파기 개체에 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CStatic`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="create"></a>CStatic::Create  
 Windows 정적 컨트롤을 만들고 연결 하는 `CStatic` 개체입니다.  
  
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
 정적 컨트롤의 창 스타일을 지정합니다. 모든 조합의 적용 [정적 컨트롤 스타일](../../mfc/reference/static-styles.md) 컨트롤에 있습니다.  
  
 `rect`  
 정적 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 `RECT` 구조 또는 `CRect` 개체입니다.  
  
 `pParentWnd`  
 지정 된 `CStatic` 부모 창, 일반적으로 `CDialog` 개체입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 정적 컨트롤의 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CStatic` 두 단계에서는 개체입니다. 먼저 생성자를 호출 `CStatic`, 다음 호출 **만들기**, Windows 정적 컨트롤을 만들고에 연결 하는 `CStatic` 개체입니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/window-styles.md) 정적 컨트롤에:  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** 일반적으로  
  
- **WS_DISABLED** 거의  
  
 다음 중 하나를 적용 해야 정적 컨트롤에는 비트맵, 커서, 아이콘 또는 메타 파일을 표시 하려는 경우 [정적 스타일](../../mfc/reference/static-styles.md):  
  
- **SS_BITMAP** 비트맵에 대 한이 스타일을 사용 합니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 사용 합니다.  
  
- **SS_ENHMETAFILE** 향상 된 메타 파일에 대 한이 스타일을 사용 합니다.  
  
 커서, 비트맵, 아이콘, 다음과 같은 스타일을 사용할 수도 있습니다.  
  
- **SS_CENTERIMAGE** 정적 컨트롤에서 이미지를 가운데 맞춤 하려면 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&1;](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]  
  
##  <a name="cstatic"></a>CStatic::CStatic  
 `CStatic` 개체를 생성합니다.  
  
```  
CStatic();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&2;](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]  
  
##  <a name="drawitem"></a>CStatic::DrawItem  
 소유자가 그린 정적 컨트롤 그리기를 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) 구조입니다. 구조에 그릴 항목 및 필요한 드로잉의 종류에 대 한 정보가 들어 있습니다.  
  
### <a name="remarks"></a>주의  
 소유자가 그린에 대 한 그리기를 구현 하려면이 함수를 재정의할 **CStatic** 개체 (컨트롤에 스타일이 **SS_OWNERDRAW**).  
  
##  <a name="getbitmap"></a>CStatic::GetBitmap  
 이전에 설정 된 비트맵의 핸들을 가져옵니다 [SetBitmap](#setbitmap), 즉 연결 된 `CStatic`합니다.  
  
```  
HBITMAP GetBitmap() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 비트맵에 대 한 핸들 또는 **NULL** 없는 비트맵에 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="getcursor"></a>CStatic::GetCursor  
 이전에 설정 된 커서의 핸들을 가져옵니다 [SetCursor](#setcursor), 즉 연결 된 `CStatic`합니다.  
  
```  
HCURSOR GetCursor();
```  
  
### <a name="return-value"></a>반환 값  
 현재 커서에 대 한 핸들 또는 **NULL** 없는 커서에 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="getenhmetafile"></a>CStatic::GetEnhMetaFile  
 이전에 설정 된 확장된 메타 파일의 핸들을 가져옵니다 [SetEnhMetafile](#setenhmetafile), 즉 연결 된 `CStatic`합니다.  
  
```  
HENHMETAFILE GetEnhMetaFile() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 확장된 메타 파일에 대 한 핸들 또는 **NULL** 없는 확장된 메타 파일에 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="geticon"></a>CStatic::GetIcon  
 으로 이전에 설정 하는 아이콘의 핸들을 가져옵니다 [SetIcon](#seticon), 즉 연결 된 `CStatic`합니다.  
  
```  
HICON GetIcon() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 아이콘에 대 한 핸들 또는 **NULL** 아이콘이 없는 설정 된 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
##  <a name="setbitmap"></a>CStatic::SetBitmap  
 새로운 비트맵 정적 컨트롤과 연결 시킵니다.  
  
```  
HBITMAP SetBitmap(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `hBitmap`  
 정적 컨트롤에 그릴 비트맵의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 정적 컨트롤을 이전에 연결 하는 비트맵의 핸들 또는 `NULL` 없는 비트맵 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>주의  
 비트맵 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 그려질 수 이며, 비트맵의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 정적 컨트롤 스타일,이 포함 하 여 사용할 수 있습니다.  
  
-   SS_BITMAP은 비트맵에 대 한 항상이 스타일을 사용 합니다.  
  
-   정적 컨트롤에서 이미지를 가운데 맞춤 하려면 SS_CENTERIMAGE 사용 됩니다. 이미지가 정적 컨트롤 보다 큰 경우 잘립니다. 정적 컨트롤 보다 작은 경우에 이미지의 빈 공간 비트맵의 왼쪽된 위 모퉁이에 있는 픽셀 색에 따라 채워집니다.  
  
-   클래스를 제공 하는 MFC `CBitmap`, 수행 보다 Win32 호출 보다는 비트맵 이미지와 함께 작동 해야 할 때 사용할 수 있는 `LoadBitmap`합니다. `CBitmap`를 한 종류의 GDI 개체를 포함 하는 대개 협력 하 여 `CStatic`, 즉는 `CWnd` 정적 컨트롤 그래픽 개체를 표시 하는 중에 사용 되는 클래스입니다.  
  
 `CImage`더 많은 장치 독립적 비트맵 DIB ()를 쉽게 작업할 수 있도록 지 원하는 ATL/MFC 클래스가입니다. 자세한 내용은 참조 [CImage 클래스](../../atl-mfc-shared/reference/cimage-class.md)합니다.  
  
-   일반적인 사용법은 제공 `CStatic::SetBitmap` 의 HBITMAP 연산자에 의해 반환 되는 GDI 개체는 `CBitmap` 또는 `CImage` 개체입니다. 이 작업을 수행 하는 코드에 다음 줄와 유사 합니다.  
  
```  
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```  
다음 예제에서는 두 개의 `CStatic` 힙의 개체입니다. 다음을 사용 하 여 시스템 비트맵 로드 `CBitmap::LoadOEMBitmap` 및 사용 하 여 파일에서 다른 `CImage::Load`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&3;](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]  
  
##  <a name="setcursor"></a>CStatic::SetCursor  
 새 커서 이미지를 정적 컨트롤과 연결 시킵니다.  
  
```  
HCURSOR SetCursor(HCURSOR hCursor);
```  
  
### <a name="parameters"></a>매개 변수  
 `hCursor`  
 정적 컨트롤에 그릴 커서의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 정적 컨트롤과 연결 된 커서의 핸들 또는 **NULL** 커서가 없습니다 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>주의  
 커서는 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 놓입니다 하 고는 커서의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 다음을 포함 하는 정적 컨트롤 스타일을 사용할 수 있습니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 항상 사용 합니다.  
  
- **SS_CENTERIMAGE** 가운데 맞춤 정적 컨트롤을 사용 합니다. 이미지가 정적 컨트롤 보다 큰 경우 잘립니다. 정적 컨트롤 보다 작은 경우에 이미지의 빈 공간 정적 컨트롤의 배경색으로 채워집니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&4;](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]  
  
##  <a name="setenhmetafile"></a>CStatic::SetEnhMetaFile  
 새 확장된 메타 파일 이미지를 정적 컨트롤과 연결 시킵니다.  
  
```  
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMetaFile`  
 정적 컨트롤에 그릴 확장된 메타 파일의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 정적 제어와 관련 된 확장된 메타 파일의 핸들 또는 **NULL** 없는 확장된 메타 파일 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>주의  
 확장된 메타 파일 정적 컨트롤에서 자동으로 그려집니다. 확장된 메타 파일 정적 컨트롤의 크기에 맞게 크기가 조정 됩니다.  
  
 다양 한 창 및 다음을 포함 하는 정적 컨트롤 스타일을 사용할 수 있습니다.  
  
- **SS_ENHMETAFILE** 향상 된 메타 파일에 대 한이 스타일을 항상 사용 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&5;](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]  
  
##  <a name="seticon"></a>CStatic::SetIcon  
 새 아이콘 이미지를 정적 컨트롤과 연결 시킵니다.  
  
```  
HICON SetIcon(HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 `hIcon`  
 정적 컨트롤에 그려질 아이콘의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 정적 컨트롤을 이전에 연결 된 아이콘의 핸들 또는 **NULL** 아이콘이 없는 정적 컨트롤에 연결 된 경우.  
  
### <a name="remarks"></a>주의  
 아이콘 정적 컨트롤에서 자동으로 그려집니다. 기본적으로 왼쪽 위 모서리에 놓입니다 하 고 아이콘의 크기를 정적 컨트롤 크기가 조정 됩니다.  
  
 다양 한 창 및 다음을 포함 하는 정적 컨트롤 스타일을 사용할 수 있습니다.  
  
- **SS_ICON** 커서 및 아이콘에 대 한이 스타일을 항상 사용 합니다.  
  
- **SS_CENTERIMAGE** 가운데 맞춤 정적 컨트롤을 사용 합니다. 이미지가 정적 컨트롤 보다 큰 경우 잘립니다. 정적 컨트롤 보다 작은 경우에 이미지의 빈 공간 정적 컨트롤의 배경색으로 채워집니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CStatic #&6;](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]  
  
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

