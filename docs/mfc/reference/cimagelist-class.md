---
title: CImageList 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
dev_langs:
- C++
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86250968fa8f6dfd9cb1a3b9a790549f70baa569
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039118"
---
# <a name="cimagelist-class"></a>CImageList 클래스
Windows의 공용 이미지 목록 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CImageList : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CImageList::CImageList](#cimagelist)|`CImageList` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CImageList::Add](#add)|이미지 목록에는 이미지 또는 이미지를 추가합니다.|  
|[CImageList::Attach](#attach)|이미지 목록에 첨부 한 `CImageList` 개체입니다.|  
|[CImageList::BeginDrag](#begindrag)|이미지를 끌기 시작 합니다.|  
|[CImageList::Copy](#copy)|내에서 이미지를 복사는 `CImageList` 개체입니다.|  
|[CImageList::Create](#create)|이미지 목록을 초기화 하 고에 연결 된 `CImageList` 개체입니다.|  
|[CImageList::DeleteImageList](#deleteimagelist)|이미지 목록을 삭제합니다.|  
|[CImageList::DeleteTempMap](#deletetempmap)|에 의해 호출 된 [CWinApp](../../mfc/reference/cwinapp-class.md) 임시 삭제 하는 유휴 시간 처리기 `CImageList` 하 여 만든 개체 `FromHandle`합니다.|  
|[CImageList::Detach](#detach)|이미지 목록 개체에서 분리 된 `CImageList` 개체 및 이미지 목록에 대 한 핸들을 반환 합니다.|  
|[CImageList::DragEnter](#dragenter)|끌기 작업 중 업데이트를 잠그고 지정된 된 위치에서 끌기 이미지를 표시 합니다.|  
|[CImageList::DragLeave](#dragleave)|창을 잠금을 해제 하 고 창을 업데이트할 수 있도록 끌기 이미지를 숨깁니다.|  
|[CImageList::DragMove](#dragmove)|끌어서 놓기 작업 중 끌고 있는 이미지를 이동 합니다.|  
|[CImageList::DragShowNolock](#dragshownolock)|표시 하거나 창을 잠그지 않고 끌기 작업 중 끌기 이미지를 숨깁니다.|  
|[CImageList::Draw](#draw)|끌어서 놓기 작업 중 끌고 있는 이미지를 그립니다.|  
|[CImageList::DrawEx](#drawex)|지정된 된 디바이스 컨텍스트에서 이미지 목록 항목을 그립니다. 지정 된 그리기 스타일을 사용 하 고 지정 된 색을 사용 하 여 이미지를 혼합 합니다.|  
|[CImageList::DrawIndirect](#drawindirect)|이미지 목록에서 이미지를 그립니다.|  
|[CImageList::EndDrag](#enddrag)|끌기 작업을 종료합니다.|  
|[CImageList::ExtractIcon](#extracticon)|이미지 및 이미지 목록에서 마스크에 따라 아이콘을 만듭니다.|  
|[CImageList::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CImageList` 개체 이미지 목록에 대 한 핸들을 지정 합니다. `CImageList` 개체가 핸들에 연결되지 않은 경우 임시 `CImageList` 개체를 만들어 연결합니다.|  
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|에 대 한 포인터를 반환 합니다.는 `CImageList` 개체 이미지 목록에 대 한 핸들을 지정 합니다. 경우는 `CImageList` 개체가 핸들에 연결 되지 않은 **NULL** 반환 됩니다.|  
|[CImageList::GetBkColor](#getbkcolor)|이미지 목록에 대 한 현재 배경색을 검색합니다.|  
|[CImageList::GetDragImage](#getdragimage)|끌어에 사용 되는 임시 이미지 목록을 가져옵니다.|  
|[CImageList::GetImageCount](#getimagecount)|이미지 목록의 이미지의 수를 검색 합니다.|  
|[CImageList::GetImageInfo](#getimageinfo)|이미지에 대 한 정보를 검색합니다.|  
|[CImageList::GetSafeHandle](#getsafehandle)|검색 **m_hImageList**합니다.|  
|[CImageList::Read](#read)|보관 파일에서 이미지 목록을 읽습니다.|  
|[CImageList::Remove](#remove)|이미지 목록에서 이미지를 제거합니다.|  
|[CImageList::Replace](#replace)|이미지 목록에서 이미지를 새 이미지로 바꿉니다.|  
|[CImageList::SetBkColor](#setbkcolor)|이미지 목록에 대 한 배경색을 설정합니다.|  
|[CImageList::SetDragCursorImage](#setdragcursorimage)|새 끌기 이미지를 만듭니다.|  
|[CImageList::SetImageCount](#setimagecount)|이미지 목록의 이미지의 수를 다시 설정합니다.|  
|[CImageList::SetOverlayImage](#setoverlayimage)|오버레이 마스크도 사용할 이미지의 목록에 있는 이미지의 0부터 시작 하는 인덱스를 추가 합니다.|  
|[CImageList::Write](#write)|이미지 목록을 보관 파일에 씁니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CImageList::operator HIMAGELIST](#operator_himagelist)|반환 된 `HIMAGELIST` 에 연결 된는 `CImageList`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CImageList::m_hImageList](#m_himagelist)|이 개체에 연결 된 이미지 목록을 포함 하는 핸들입니다.|  
  
## <a name="remarks"></a>설명  
 "이미지 목록"는 컬렉션의 동일한 크기의 이미지는 각각 0부터 시작 인덱스로 참조할 수 있습니다. 이미지 목록 큰 집합 아이콘이 나 비트맵을 효율적으로 관리 하는 데 사용 됩니다. 모든 이미지는 이미지 목록에서 화면 장치 형식에서 단일, 와이드 비트맵에 포함 됩니다. 이미지 목록의 이미지를 그리는 투명 하 게 사용 하는 마스크 (아이콘 스타일)를 포함 하는 단색 비트맵을 포함할 수도 있습니다. Microsoft Win32 응용 프로그래밍 인터페이스 (API) 이미지를 그릴, 만들고 이미지 목록을 삭제, 추가 및 이미지 제거, 이미지를 바꿔야, 이미지, 병합 및 이미지 끌 수 있도록 하는 이미지 목록 기능을 제공 합니다.  
  
 이 컨트롤 (및 따라서는 `CImageList` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CImageList`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CImageList 사용 하 여](../../mfc/using-cimagelist.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CImageList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="add"></a>  CImageList::Add  
 이미지 목록에 하나 이상의 이미지 또는 아이콘을 추가 하려면이 함수를 호출 합니다.  
  
```  
int Add(
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Add(
    CBitmap* pbmImage,  
    COLORREF crMask);  
  
int Add(HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbmImage*  
 이미지를 포함 하는 비트맵에 대 한 포인터입니다. 이미지의 수는 비트맵의 너비에서 유추 됩니다.  
  
 *pbmMask*  
 마스크가 포함 된 비트맵에 대 한 포인터입니다. 마스크가 없습니다 이미지 목록을 사용 하 여 사용 하는 경우이 매개 변수가 무시 됩니다.  
  
 *crMask*  
 마스크를 생성 하는 데 사용 하는 색입니다. 각 픽셀의 지정한 비트맵에서이 색이 검정색으로 변경 되 고 해당 비트 마스크의 하나로 설정 됩니다.  
  
 *hIcon*  
 비트맵 및 새 이미지에 대 한 마스크를 포함 하는 아이콘의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 첫 번째 새 이미지의 인덱스 0부터 시작 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 완료 되 면 아이콘 핸들을 해제 책임이 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]  
  
##  <a name="attach"></a>  CImageList::Attach  
 이미지 목록에 연결 하려면이 함수 호출을 `CImageList` 개체입니다.  
  
```  
BOOL Attach(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 *hImageList*  
 이미지 목록 개체에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 첨부 파일에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]  
  
##  <a name="begindrag"></a>  CImageList::BeginDrag  
 이미지를 끌기 시작 하려면이 함수를 호출 합니다.  
  
```  
BOOL BeginDrag(
    int nImage,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 끌어 이미지의 인덱스 0부터 시작 합니다.  
  
 *ptHotSpot*  
 좌표 시작 끌어서 위치 (일반적으로 커서 위치)입니다. 좌표는 이미지의 왼쪽된 위 모퉁이 기준으로 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 끌어에 사용 되는 임시 이미지 목록을 만듭니다. 이미지는 현재 커서와 지정된 된 이미지 및 마스크를 결합합니다. 다음에 대 한 응답 `WM_MOUSEMOVE` 메시지를 사용 하 여 끌기 이미지를 이동할 수 있습니다는 `DragMove` 멤버 함수입니다. 끌기 작업을 종료 하려면 사용할 수 있습니다는 `EndDrag` 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]  
  
##  <a name="cimagelist"></a>  CImageList::CImageList  
 `CImageList` 개체를 생성합니다.  
  
```  
CImageList();
```  
  
##  <a name="copy"></a>  CImageList::Copy  
 이 멤버 함수는 Win32 함수의 동작을 구현 [ImageList_Copy](http://msdn.microsoft.com/library/windows/desktop/bb761520)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL Copy(
    int iDst,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);

 
BOOL Copy(
    int iDst,  
    CImageList* pSrc,  
    int iSrc,  
    UINT uFlags = ILCF_MOVE);
```  
  
### <a name="parameters"></a>매개 변수  
 *iDst*  
 복사 작업의 대상으로 사용할 이미지의 0부터 시작 하는 인덱스입니다.  
  
 *iSrc*  
 복사 작업의 원본으로 사용할 이미지의 0부터 시작 하는 인덱스입니다.  
  
 *uFlags*  
 복사 작업 수의 형식을 지정 하는 비트 플래그 값입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|`ILCF_MOVE`|소스 이미지 대상 이미지의 인덱스에 복사 됩니다. 이 작업으로 인해 지정된 된 이미지의 여러 인스턴스. 기본값은 `ILCF_MOVE`입니다.|  
|`ILCF_SWAP`|소스와 대상 이미지는 이미지 목록 내에서 위치를 교환합니다.|  
  
 *pSrc*  
 에 대 한 포인터는 `CImageList` 복사 작업의 대상인 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]  
  
##  <a name="create"></a>  CImageList::Create  
 이미지 목록을 초기화 하 고에 연결 된 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다.  
  
```  
BOOL Create(
    int cx,  
    int cy,  
    UINT nFlags,  
    int nInitial,  
    int nGrow);

 
BOOL Create(
    UINT nBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    LPCTSTR lpszBitmapID,  
    int cx,  
    int nGrow,  
    COLORREF crMask);

 
BOOL Create(
    CImageList& imagelist1,  
    int nImage1,  
    CImageList& imagelist2,  
    int nImage2,  
    int dx,  
    int dy);  
  
BOOL Create(CImageList* pImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 *cx*  
 픽셀 단위로 각 이미지의 크기입니다.  
  
 *cy*  
 픽셀 단위로 각 이미지의 크기입니다.  
  
 *nFlags*  
 만들려는 이미지 목록의 유형을 지정 합니다. 이 매개 변수는 다음 값의 조합 수 있지만 중 하나만 포함할 수 있습니다는 `ILC_COLOR` 값입니다.  
  
|값|의미|  
|-----------|-------------|  
|`ILC_COLOR`|다른 없는 경우 기본 동작을 사용 하 여 `ILC_COLOR`* 플래그 지정 합니다. 기본값은 일반적으로 `ILC_COLOR4`; 이전 디스플레이 드라이버에 대 한 기본값은 있지만 `ILC_COLORDDB`합니다.|  
|`ILC_COLOR4`|이미지 목록에 대 한 비트맵으로 4 비트 (16 개의 색) 장치 독립적 비트맵 (DIB) 절을 사용 합니다.|  
|`ILC_COLOR8`|8 비트 DIB 섹션을 사용 합니다. 색상표에 사용 되는 색깔이 하프톤 팔레트와 같은 색입니다.|  
|`ILC_COLOR16`|16 비트를 사용 하 여 (32/64 k 색) DIB 섹션.|  
|`ILC_COLOR24`|24 비트 DIB 섹션을 사용 합니다.|  
|`ILC_COLOR32`|32 비트 DIB 섹션을 사용 합니다.|  
|`ILC_COLORDDB`|장치 종속적 비트맵을 사용 합니다.|  
|`ILC_MASK`|마스크를 사용 합니다. 이미지 목록에는 두 개의 비트맵, 그 중 하나는 마스크로 사용 단색 비트맵을 포함 되어 있습니다. 이 값이 포함 되지 않은 경우 이미지 목록 하나만 비트맵을 포함 합니다. 참조 [이미지 목록에서 이미지 그리기](../../mfc/drawing-images-from-an-image-list.md) 마스크 된 이미지에 대 한 자세한 내용은 합니다.|  
  
 *nInitial*  
 이미지 목록에 처음 포함 되어 있는 이미지의 수입니다.  
  
 *nGrow*  
 기준인 시스템에서 새 이미지에 대 한 공간을 만들기 위해 목록의 크기를 조정 해야 할 경우 이미지 목록을 증가할 수 이미지의 수입니다. 이 매개 변수 크기가 조정 된 이미지 목록을 포함할 수는 새 이미지의 수를 나타냅니다.  
  
 *nBitmapID*  
 이미지 목록에 연관 될 비트맵의 리소스 Id입니다.  
  
 *crMask*  
 마스크를 생성 하는 데 사용 하는 색입니다. 각 픽셀의 지정한 비트맵에서이 색이 검정색으로 변경 되 고 해당 비트 마스크의 하나로 설정 됩니다.  
  
 *lpszBitmapID*  
 이미지의 리소스 Id를 포함 하는 문자열입니다.  
  
 *imagelist1*  
 `CImageList` 개체에 대한 참조입니다.  
  
 *nImage1*  
 첫 번째 기존 이미지의 인덱스입니다.  
  
 *imagelist2*  
 `CImageList` 개체에 대한 참조입니다.  
  
 *nImage2*  
 두 번째 기존 이미지의 인덱스입니다.  
  
 *dx*  
 첫 번째 이미지 픽셀의 관계에서 두 번째 이미지의 x 축 오프셋입니다.  
  
 *dy*  
 첫 번째 이미지 픽셀의 관계에서 두 번째 이미지의 y 축을의 오프셋입니다.  
  
 *pImageList*  
 에 대 한 포인터는 `CImageList` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성 한 `CImageList` 두 단계를 수행에서 합니다. 먼저 생성자를 호출 하 고 호출 `Create`, 이미지 목록을 만들고 하는에 연결 된 `CImageList` 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]  
  
##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList  
 이미지 목록을 삭제 하려면이 함수를 호출 합니다.  
  
```  
BOOL DeleteImageList();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]  
  
##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap  
 자동으로 호출는 `CWinApp` 유휴 시간 처리기 `DeleteTempMap` 임시 삭제 `CImageList` 가 만든 개체 [FromHandle](#fromhandle), 핸들을 모두 삭제 하지 않습니다 ( `hImageList`) 일시적으로 연결 와 **ImageList** 개체입니다.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]  
  
##  <a name="detach"></a>  CImageList::Detach  
 이 함수는 이미지 목록 개체에서 분리를 호출 하는 `CImageList` 개체입니다.  
  
```  
HIMAGELIST Detach();
```  
  
### <a name="return-value"></a>반환 값  
 이미지 목록 개체에 대 한 핸들입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 이미지 목록 개체에 대 한 핸들을 반환합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::Attach](#attach)합니다.  
  
##  <a name="dragenter"></a>  CImageList::DragEnter  
 끌기 작업 중 지정 된 창에 대 한 업데이트를 잠급니다 *pWndLock* 하 여 지정 된 위치에서 끌기 이미지를 표시 하 고 *가리킨*합니다.  
  
```  
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,  
    CPoint point);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndLock*  
 끌기 이미지를 소유 하는 창에 대 한 포인터입니다.  
  
 *지점*  
 끌기 이미지를 표시할 위치입니다. 좌표는 (클라이언트 영역 제외) 창의 왼쪽된 위 모퉁이 기준으로 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 좌표 창의 왼쪽된 위 모퉁이 기준으로 되므로 좌표를 지정 하는 경우의 테두리, 제목 표시줄 및 메뉴 모음 같은 창 요소의 너비에 대 한 보완 해야 합니다.  
  
 경우 *pWndLock* 은 **NULL**,이 함수는 데스크톱 창에 연결 된 디스플레이 컨텍스트에 이미지를 그립니다 및 좌표는 화면의 왼쪽된 위 모퉁이 기준으로 합니다.  
  
 이 함수는 끌기 작업 중 지정된 된 창에 다른 모든 업데이트를 잠급니다. 끌어서 놓기 작업의 대상 강조 하는 등의 끌기 작업 중에 그리기를 수행 해야 할 경우 임시로 숨길 수 있습니다 끌어온된 이미지를 사용 하 여는 [CImageList::DragLeave](#dragleave) 함수입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::BeginDrag](#begindrag)합니다.  
  
##  <a name="dragleave"></a>  CImageList::DragLeave  
 지정한 창과 잠금을 해제 *pWndLock* 하 고 업데이트할 수 있는 창을 끌기 이미지를 숨깁니다.  
  
```  
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndLock*  
 끌기 이미지를 소유 하는 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::EndDrag](#enddrag)합니다.  
  
##  <a name="dragmove"></a>  CImageList::DragMove  
 끌어서 놓기 작업 중 끌고 있는 이미지를 이동 하려면이 함수를 호출 합니다.  
  
```  
static BOOL PASCAL DragMove(CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 *pt*  
 새 끌어서 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 일반적으로 대 한 응답으로 호출 됩니다는 `WM_MOUSEMOVE` 메시지입니다. 끌기 작업을 시작 하려면 사용 하 여는 `BeginDrag` 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]  
  
##  <a name="dragshownolock"></a>  CImageList::DragShowNolock  
 표시 하거나 창을 잠그지 않고 끌기 작업 중 끌기 이미지를 숨깁니다.  
  
```  
static BOOL PASCAL DragShowNolock(BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 *bShow*  
 끌기 이미지를 표시할 수 있는지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 [CImageList::DragEnter](#dragenter) 함수 끌기 작업 중 창에 모든 업데이트를 잠급니다. 하지만이 기능을 잠그지 않습니다 창.  
  
##  <a name="draw"></a>  CImageList::Draw  
 끌어서 놓기 작업 중 끌고 있는 이미지를 그릴이 함수를 호출 합니다.  
  
```  
BOOL Draw(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 대상 장치 컨텍스트에 대 한 포인터입니다.  
  
 *nImage*  
 그릴 이미지의 인덱스 0부터 시작 합니다.  
  
 *pt*  
 위치를 지정된 된 디바이스 컨텍스트 그릴입니다.  
  
 *nStyle*  
 그리기 스타일을 지정 하는 플래그입니다. 이러한 값 중 하나 이상을 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|`ILD_BLEND25`**ILD_FOCUS**|25% 시스템 강조 색을 혼합 이미지를 그립니다. 이미지 목록에는 마스크 없는 경우에이 값 효과가 없습니다.|  
|`ILD_BLEND50`**ILD_SELECTED**, **ILD_BLEND**|50% 시스템 강조 색을 혼합 이미지를 그립니다. 이미지 목록에는 마스크 없는 경우에이 값 효과가 없습니다.|  
|`ILD_MASK`|/ / 마스크를 그립니다.|  
|`ILD_NORMAL`|명령 프롬프트 창의 배경색을 사용 하 여 이미지 목록의 이미지를 그립니다. 배경색은 하는 경우는 `CLR_NONE` 값, 이미지를 투명 하 게 / / 마스크를 사용 하 여 그려집니다.|  
|`ILD_TRANSPARENT`|투명 하 게 배경색에 관계 없이 마스크를 사용 하 여 이미지를 그립니다.|  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::SetOverlayImage](#setoverlayimage)합니다.  
  
##  <a name="drawex"></a>  CImageList::DrawEx  
 지정된 된 디바이스 컨텍스트에서 이미지 목록 항목을 그립니다.  
  
```  
BOOL DrawEx(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    COLORREF clrBk,  
    COLORREF clrFg,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 대상 장치 컨텍스트에 대 한 포인터입니다.  
  
 *nImage*  
 그릴 이미지의 인덱스 0부터 시작 합니다.  
  
 *pt*  
 위치를 지정된 된 디바이스 컨텍스트 그릴입니다.  
  
 *sz*  
 이미지의 왼쪽 위 모퉁이 기준으로 그릴 이미지의 부분의 크기입니다. 참조 *dx* 및 *dy* 에 [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows sdk에서입니다.  
  
 *clrBk*  
 이미지의 배경색입니다. 참조 *rgbBk* 에 [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows sdk에서입니다.  
  
 *clrFg*  
 이미지의 전경색입니다. 참조 *rgbFg* 에 [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows sdk에서입니다.  
  
 *nStyle*  
 그리기 스타일을 지정 하는 플래그입니다. 참조 *fStyle* 에 [ImageList_DrawEx](http://msdn.microsoft.com/library/windows/desktop/bb761536) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 지정 된 그리기 스타일을 사용 하 고 지정 된 색을 사용 하 여 이미지를 혼합 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]  
  
##  <a name="drawindirect"></a>  CImageList::DrawIndirect  
 이미지 목록에서 이미지를 그리기 위해이 함수를 호출 합니다.  
  
```  
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

 
BOOL DrawIndirect(
    CDC* pDC,  
    int nImage,  
    POINT pt,  
    SIZE sz,  
    POINT ptOrigin,  
    UINT fStyle = ILD_NORMAL,  
    DWORD dwRop = SRCCOPY,  
    COLORREF rgbBack = CLR_DEFAULT,  
    COLORREF rgbFore = CLR_DEFAULT,  
    DWORD fState = ILS_NORMAL,  
    DWORD Frame = 0,  
    COLORREF crEffect = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>매개 변수  
 *pimldp*  
 에 대 한 포인터는 [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) 그리기 작업에 대 한 정보가 포함 된 구조체입니다.  
  
 *pDC*  
 대상 장치 컨텍스트에 대 한 포인터입니다. 이 삭제 해야 [CDC](../../mfc/reference/cdc-class.md) 을 마쳤을 때 개체입니다.  
  
 *nImage*  
 그릴 이미지의 0부터 시작 하는 인덱스입니다.  
  
 *pt*  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 는 x 및 y 좌표 이미지를 그릴 위치를 포함 하는 구조입니다.  
  
 *sz*  
 A [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 그릴 이미지의 크기를 나타내는 구조입니다.  
  
 *ptOrigin*  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 는 x 및 y 좌표 이미지 자체와 관련 하 여 그리기 작업의 왼쪽된 위 모퉁이 지정 합니다. 포함 된 구조체입니다. 이미지의 x 좌표 및 y-좌표 위에 왼쪽에 있는 픽셀 그려집니다.  
  
 *fStyle*  
 그리기 스타일 및 필요에 따라 오버레이 이미지를 지정 하는 플래그입니다. 오버레이 이미지에 자세한 내용은 설명 섹션을 참조 하십시오. MFC 기본 구현은 `ILD_NORMAL`, 명령 프롬프트 창의 배경색을 사용 하 여 이미지 목록의 이미지를 그립니다. 배경색은 하는 경우는 `CLR_NONE` 값, 이미지를 투명 하 게 마스크를 사용 하 여 그려집니다.  
  
 다른 가능한 스타일에 설명 되어는 *fStyle* 의 멤버는 [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) 구조입니다.  
  
 *dwRop*  
 래스터 작업 코드를 지정 하는 값입니다. 이러한 코드 최종 색상을 달성 하기 위해 대상 사각형에 대 한 색 데이터와 소스 사각형에 대 한 색 데이터를 결합 하는 방법을 정의 합니다. MFC의 기본 구현, **SRCCOPY**, 소스 사각형 대상 사각형에 직접 복사 합니다. 이 매개 변수는 *fStyle* 매개 변수가 포함 되지 않습니다는 **ILD_ROP** 플래그입니다.  
  
 다른 가능한 값은 아래 설명의 *dwRop* 의 멤버는 [IMAGELISTDRAWPARAMS](http://msdn.microsoft.com/library/windows/desktop/bb761395) 구조입니다.  
  
 *rgbBack*  
 기본적으로 배경색 이미지 `CLR_DEFAULT`합니다. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|`CLR_DEFAULT`|기본 배경색입니다. 이미지의 이미지 목록 배경색을 사용 하 여 그려집니다.|  
|`CLR_NONE`|없음 배경색입니다. 이미지를 그릴 투명 하 게 합니다.|  
  
 *rgbFore*  
 전경색, 기본적으로 이미지 `CLR_DEFAULT`합니다. 이 매개 변수는 응용 프로그램 정의 RGB 값 또는 다음 값 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|`CLR_DEFAULT`|기본 전경색입니다. 이미지는 시스템 강조 색을 사용 하 여 전경색으로 그려집니다.|  
|`CLR_NONE`|Blend 색이 없습니다. 대상 장치 컨텍스트에의 색으로 혼합 됩니다.|  
  
 경우에이 매개 변수는 *fStyle* 포함는 `ILD_BLEND25` 또는 `ILD_BLEND50` 플래그입니다.  
  
 *fState*  
 그리기 상태를 지정 하는 플래그입니다. 이 멤버는 하나 이상의 이미지 목록 상태 플래그를 포함할 수 있습니다.  
  
 *프레임*  
 Saturate 및 알파 혼합 효과의 동작을 영향을 줍니다.  
  
 와 함께 사용할 경우 **ILS_SATURATE**를이 멤버는 아이콘에 있는 각 픽셀에 대 한 RGB 세 개의 각 색상 구성 요소에 추가 되는 값을가지고 있습니다.  
  
 와 함께 사용할 경우 **ILS_APLHA**를이 멤버는 알파 채널에 대 한 값을 보유 합니다. 이 값은 0에서 255 사이의 0 완전히 투명이 고 255 완전히 불투명 수 있습니다.  
  
 *crEffect*  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 광선 및 그림자 효과 대해 사용 되는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 이미지 상태가 성공적으로 그린 아니면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전을 사용 하 여 Win32 구조를 직접 입력 하려는 경우. 두 번째 버전을 사용 하 여 하나 이상의 MFC의 기본 인수를 활용 하기 위해 또는 구조를 관리 하지 않도록 하려는 경우.  
  
 오버레이 이미지는이 멤버 함수에 지정 된 기본 이미지 위에 그려지는 이미지의 *nImage* 매개 변수입니다. 오버레이 마스크를 사용 하 여 그리기는 [그리기](#draw) 멤버 함수를 사용 하 여 지정 된 오버레이 마스크의 1부터 시작 인덱스는 [INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) 매크로입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]  
  
##  <a name="enddrag"></a>  CImageList::EndDrag  
 끌기 작업을 종료 하려면이 함수를 호출 합니다.  
  
```  
static void PASCAL EndDrag();
```  
  
### <a name="remarks"></a>설명  
 끌기 작업을 시작 하려면 사용 하 여는 `BeginDrag` 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]  
  
##  <a name="extracticon"></a>  CImageList::ExtractIcon  
 이미지 및 이미지 목록에서 관련 된 마스크에 따라 아이콘을 만드는이 함수를 호출 합니다.  
  
```  
HICON ExtractIcon(int nImage);
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 이미지의 인덱스 0부터 시작 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 아이콘의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 방법은의 동작에 의존는 [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) 아이콘을 만드는 매크로입니다. 참조는 [ImageList_ExtractIcon](http://msdn.microsoft.com/library/windows/desktop/bb761401) 아이콘 생성 및 정리에 대 한 자세한 내용은 매크로입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]  
  
##  <a name="fromhandle"></a>  CImageList::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CImageList` 개체 이미지 목록에 대 한 핸들을 지정 합니다.  
  
```  
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 *hImageList*  
 이미지 목록을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CImageList` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CImageList` 이미 임시 핸들에 연결 되지 않은 `CImageList` 개체가 생성 되 고 연결 합니다. 이 임시 `CImageList` 개체는 다음에 응용 프로그램의 경우 이벤트 루프 유휴 시간에 인 될 때까지 시간에 모든 임시 개체를 삭제만 유효 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]  
  
##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent  
 에 대 한 포인터를 반환 합니다.는 `CImageList` 개체 이미지 목록에 대 한 핸들을 지정 합니다.  
  
```  
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 *hImageList*  
 이미지 목록을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CImageList` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CImageList` 개체가 핸들에 연결 되지 않은 **NULL** 반환 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]  
  
##  <a name="getbkcolor"></a>  CImageList::GetBkColor  
 이미지 목록에 대 한 현재 배경색을 검색 하려면이 함수를 호출 합니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색상 값의는 `CImageList` 배경 색 개체입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::SetBkColor](#setbkcolor)합니다.  
  
##  <a name="getdragimage"></a>  CImageList::GetDragImage  
 끌어에 사용 되는 임시 이미지 목록을 가져옵니다.  
  
```  
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,  
    LPPOINT lpPointHotSpot);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpPoint*  
 주소는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 끌어 위치를 구조체 현재입니다.  
  
 *lpPointHotSpot*  
 주소는 **지점** 구조체 끌어서 위치를 기준으로 끌기 이미지의 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 임시 이미지에 대 한 포인터를 나열 하는 끌어;에 대 한 사용 그렇지 않으면 **NULL**합니다.  
  
##  <a name="getimagecount"></a>  CImageList::GetImageCount  
 이미지 목록에서 이미지의 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetImageCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이미지의 수입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::ExtractIcon](#extracticon)합니다.  
  
##  <a name="getimageinfo"></a>  CImageList::GetImageInfo  
 이미지에 대 한 정보를 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetImageInfo(
    int nImage,  
    IMAGEINFO* pImageInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 이미지의 인덱스 0부터 시작 합니다.  
  
 *pImageInfo*  
 에 대 한 포인터는 [IMAGEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761393) 구조체 이미지에 대 한 정보입니다. 이미지에 대 한 비트맵을 직접 조작 하이 구조에서 정보를 사용할 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `IMAGEINFO` 구조 이미지는 이미지 목록에서에 대 한 정보를 포함 합니다.  
  
##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle  
 검색 하려면이 함수 호출의 **m_hImageList** 데이터 멤버입니다.  
  
```  
HIMAGELIST GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 연결 된 이미지 목록;에 대 한 핸들 그렇지 않으면 **NULL** 개체가 연결 된 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]  
  
##  <a name="m_himagelist"></a>  CImageList::m_hImageList  
 이 개체에 연결 된 이미지 목록의 처리 합니다.  
  
 **HIMAGELIST m_hImageList;**  
  
### <a name="remarks"></a>설명  
 **m_hImageList** 데이터 멤버는 형식의 공용 변수 `HIMAGELIST`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]  
  
##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST  
 이 연산자를 사용 하 여의 연결 된 핸들을 가져올 수는 `CImageList` 개체입니다.  
  
```  
operator HIMAGELIST() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우 성공 이미지 목록에 대 한 핸들 나타내는 `CImageList` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는의 직접 사용을 지원 하려면 캐스팅 연산자는 `HIMAGELIST` 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]  
  
##  <a name="read"></a>  CImageList::Read  
 보관 파일에서 이미지 목록을 읽을 수이 함수를 호출 합니다.  
  
```  
BOOL Read(CArchive* pArchive);
```  
  
### <a name="parameters"></a>매개 변수  
 *pArchive*  
 에 대 한 포인터는 `CArchive` 이미지 목록의 읽을 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]  
  
##  <a name="remove"></a>  CImageList::Remove  
 이미지 목록 개체에서 이미지를 제거 하려면이 함수를 호출 합니다.  
  
```  
BOOL Remove(int nImage);
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 제거할 이미지의 인덱스 0부터 시작 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 다음 모든 항목 *nImage* 이제 한 칸 아래로 이동 합니다. 예를 들어 이미지 목록에 두 개의 항목이 있으면 첫 번째 항목을 삭제 하면 나머지 항목을 첫 번째 위치에 모두 포함 됩니다. *nImage*= 첫 번째 위치에 있는 항목에 대 한 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]  
  
##  <a name="replace"></a>  CImageList::Replace  
 이미지 목록에서 이미지를 새 이미지로 대체 하려면이 함수를 호출 합니다.  
  
```  
BOOL Replace(
    int nImage,  
    CBitmap* pbmImage,  
    CBitmap* pbmMask);

 
int Replace(
    int nImage,  
    HICON hIcon);
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 바꿀 이미지의 인덱스 0부터 시작 합니다.  
  
 *pbmImage*  
 이미지가 포함 된 비트맵에 대 한 포인터입니다.  
  
 *pbmMask*  
 / / 마스크를 포함 하는 비트맵에 대 한 포인터입니다. 마스크가 없습니다 이미지 목록을 사용 하 여 사용 하는 경우이 매개 변수가 무시 됩니다.  
  
 *hIcon*  
 비트맵 및 새 이미지에 대 한 마스크를 포함 하는 아이콘에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 되는 버전 **BOOL** 성공 하면 그렇지 않으면 0 0이 아닌 값을 반환 합니다.  
  
 반환 되는 버전 **int** 성공 되지 않으면-이미지의 0부터 시작 하는 인덱스를 반환 합니다. 1.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 호출한 후 호출 [SetImageCount](#setimagecount) 새를 할당 하려면 자리 표시자를 유효한 이미지의 인덱스 번호를 이미지입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CImageList::SetImageCount](#setimagecount)합니다.  
  
##  <a name="setbkcolor"></a>  CImageList::SetBkColor  
 이미지 목록에 대 한 배경색을 설정 하려면이 함수를 호출 합니다.  
  
```  
COLORREF SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 *cr*  
 배경색을 설정 합니다. 것이 `CLR_NONE`합니다. 이 경우 이미지를 투명 하 게 / / 마스크를 사용 하 여 그립니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 이전 배경색 그렇지 않으면 `CLR_NONE`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]  
  
##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage  
 현재 끌기 이미지와 지정 된 이미지 (일반적으로 마우스 커서 이미지)를 결합 하 여 새 끌기 이미지를 만듭니다.  
  
```  
BOOL SetDragCursorImage(
    int nDrag,  
    CPoint ptHotSpot);
```  
  
### <a name="parameters"></a>매개 변수  
 *nDrag*  
 끌기 이미지와 함께 사용할 새 이미지의 인덱스입니다.  
  
 *ptHotSpot*  
 새 이미지 내 핫 스폿 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 Windows를 사용 해야 끌기 함수가 끌기 작업 중 새 이미지를 사용 하므로 [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) 함수를 호출한 후 실제 마우스 커서를 숨기려면 `CImageList::SetDragCursorImage`합니다. 그렇지 않은 경우 시스템은 끌기 작업의 기간에 대 한 두 개의 마우스 커서를 가져야 나타날 수 있습니다.  
  
##  <a name="setimagecount"></a>  CImageList::SetImageCount  
 호출에서 이미지 수를 다시 설정 하려면이 함수는 `CImageList` 개체입니다.  
  
```  
BOOL SetImageCount(UINT uNewCount);
```  
  
### <a name="parameters"></a>매개 변수  
 *uNewCount*  
 이미지 목록에 새 이미지의 총 수를 지정 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이미지 목록의 이미지 수를 늘리려면이 멤버 함수를 호출 하는 경우 다음 호출 [대체](#replace) 유효한 이미지에 새 인덱스를 할당 하려면 각 추가 이미지에 대 한 합니다. 유효한 이미지에 인덱스를 할당 하지 않으면에 새 이미지를 만드는 그리기 작업을 예측할 수 없습니다.  
  
 이 함수를 사용 하 여 이미지 목록의 크기를 줄이는 경우 잘린된 이미지 해제 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]  
  
##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage  
 오버레이 마스크도 사용할 이미지의 목록에 있는 이미지의 0부터 시작 하는 인덱스를 추가 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetOverlayImage(
    int nImage,  
    int nOverlay);
```  
  
### <a name="parameters"></a>매개 변수  
 *nImage*  
 오버레이 마스크도 사용할 이미지의 인덱스 0부터 시작 합니다.  
  
 *nOverlay*  
 1부터 시작 인덱스 오버레이 마스크입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 목록에는 최대 4 개의 인덱스를 추가할 수 있습니다.  
  
 오버레이 마스크에는 다른 이미지 위에 투명 하 게 그려지는 하는 이미지입니다. 이미지 위에 오버레이 마스크를 사용 하 여 그릴는 [CImageList::Draw](#draw) 멤버 함수를 사용 하 여 지정 된 오버레이 마스크의 1부터 시작 인덱스는 **INDEXTOOVERLAYMASK** 매크로입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]  
  
##  <a name="write"></a>  CImageList::Write  
 보관 파일에 이미지 목록 개체를 작성 하려면이 함수를 호출 합니다.  
  
```  
BOOL Write(CArchive* pArchive);
```  
  
### <a name="parameters"></a>매개 변수  
 *pArchive*  
 에 대 한 포인터는 `CArchive` 이미지 목록을 저장할 인 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)   
 [CTabCtrl 클래스](../../mfc/reference/ctabctrl-class.md)
