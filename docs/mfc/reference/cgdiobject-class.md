---
title: CGdiObject 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba88269cf37f41cf8a594745eb2e98a57ccf64ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cgdiobject-class"></a>CGdiObject 클래스
비트맵, 영역, 브러시, 펜, 색상표와 글꼴 등 다양한 Windows GDI(그래픽 장치 인터페이스) 개체에 기본 클래스를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|`CGdiObject` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Windows GDI 개체에 연결 된 `CGdiObject` 개체입니다.|  
|[CGdiObject::CreateStockObject](#createstockobject)|Windows의 미리 정의 된 스톡 펜, 브러시, 또는 글꼴 중 하나에 대 한 핸들을 검색합니다.|  
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI 개체에 연결 삭제는 `CGdiObject` 개체에 연결 된 모든 시스템 저장소를 해제 하 여 메모리에서 개체입니다.|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|임시 삭제 `CGdiObject` 가 만든 개체 `FromHandle`합니다.|  
|[CGdiObject::Detach](#detach)|Windows GDI 개체를 분리 한 `CGdiObject` 개체를 Windows GDI 개체에 대 한 핸들을 반환 합니다.|  
|[CGdiObject::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CGdiObject` Windows GDI 개체에 대 한 핸들을 부여 하는 개체입니다.|  
|[CGdiObject::GetObject](#getobject)|에 연결 된 채우기는 Windows GDI 개체를 설명 하는 데이터를 사용 하 여 버퍼는 `CGdiObject` 개체입니다.|  
|[CGdiObject::GetObjectType](#getobjecttype)|GDI 개체 유형을 검색합니다.|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|반환 `m_hObject` 하지 않는 한 `this` 은 `NULL`있으며이 경우 `NULL` 반환 됩니다.|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|브러시의 원점으로 다시 설정 하거나 논리 팔레트를 다시 설정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|하는 경우 두 GDI 개체가 논리적으로 같지 않은지 확인 합니다.|  
|[CGdiObject::operator = =](#operator_eq_eq)|두 GDI 개체가 논리적으로 동일한 지를 결정 합니다.|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|검색 한 `HANDLE` 연결 된 Windows GDI 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|A `HANDLE` 포함 하는 `HBITMAP`, `HPALETTE`, `HRGN`, `HBRUSH`, `HPEN`, 또는 `HFONT` 이 개체에 연결 합니다.|  
  
## <a name="remarks"></a>설명  
 만들지 마십시오는 `CGdiObject` 직접 합니다. 대신, 개체를 만들면 해당 파생된 클래스 중 하나에서 같은 `CPen` 또는 `CBrush`합니다.  
  
 대 한 자세한 내용은 `CGdiObject`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="attach"></a>  CGdiObject::Attach  
 Windows GDI 개체에 연결 된 `CGdiObject` 개체입니다.  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 A `HANDLE` Windows GDI 개체 (예를 들어 `HPEN` 또는 `HBRUSH`).  
  
### <a name="return-value"></a>반환 값  
 첨부 파일에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject  
 `CGdiObject` 개체를 생성합니다.  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>설명  
 만들지 마십시오는 `CGdiObject` 직접 합니다. 대신, 개체를 만들면 해당 파생된 클래스 중 하나에서 같은 `CPen` 또는 **Cbrush**합니다.  
  
##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject  
 미리 정의 된 스톡 Windows GDI 펜, 브러시, 또는 글꼴 중 하나에 대 한 핸들을 검색 하 고 GDI 개체에 연결 된 `CGdiObject` 개체입니다.  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 원하는 스톡 개체의 유형을 지정 하는 상수입니다. 매개 변수 참조 *fnObject* 에 대 한 [GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925) Windows sdk에 대 한 설명은 적절 한 값입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 호출에서 파생 된 중 하나가 지정 된이 함수는 클래스와 같은 Windows GDI 개체 형식에 해당 `CPen` 스톡 펜입니다.  
  
##  <a name="deleteobject"></a>  CGdiObject::DeleteObject  
 Windows GDI 개체와 연결 된 모든 시스템 저장소를 해제 하 여 메모리에서 연결 된 Windows GDI 개체를 삭제 합니다.  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>반환 값  
 GDI 개체를 삭제 했습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 연결 된 저장소는 `CGdiObject` 개체가이 호출에 의해 영향을 받지 않습니다. 응용 프로그램을 호출 하지 않아야 `DeleteObject` 에 `CGdiObject` 현재 장치 컨텍스트로 선택 된 개체입니다.  
  
 패턴 브러시 삭제 되 면 브러시와 연결 된 비트맵 삭제 되지 않습니다. 비트맵을 독립적으로 삭제 되어야 합니다.  
  
##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap  
 자동으로 호출 된 `CWinApp` 유휴 시간 처리기 `DeleteTempMap` 임시 삭제 `CGdiObject` 가 만든 개체 `FromHandle`합니다.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>설명  
 `DeleteTempMap` 임시에 연결 하는 Windows GDI 개체를 분리 `CGdiObject` 개체를 삭제 하기 전에 `CGdiObject` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>  CGdiObject::Detach  
 Windows GDI 개체를 분리 한 `CGdiObject` 개체를 Windows GDI 개체에 대 한 핸들을 반환 합니다.  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>반환 값  
 A `HANDLE` Windows GDI 개체 분리, 그렇지 않으면 **NULL** GDI 개체가 연결 된 경우.  
  
##  <a name="fromhandle"></a>  CGdiObject::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CGdiObject` Windows GDI 개체에 대 한 핸들을 부여 하는 개체입니다.  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 A `HANDLE` Windows GDI 개체에 있습니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CGdiObject` 임시적인 지, 영구적인 문제일 수 있습니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CGdiObject` 개체가 이미 임시 Windows GDI 개체에 연결 되지 않은 `CGdiObject` 개체가 생성 되 고 연결 합니다.  
  
 이 임시 `CGdiObject` 개체는 응용 프로그램에서 모든 임시 그래픽 개체를 삭제 될 때의 이벤트 루프 유휴 시간에는 다음 때만 유효 합니다. 임시 개체가 올바른지만 한 창 메시지를 처리 하는 동안는 하는 또 다른 방법은 말하면 합니다.  
  
##  <a name="getobject"></a>  CGdiObject::GetObject  
 지정된 된 개체를 정의 하는 데이터 버퍼를 채웁니다.  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nCount`  
 에 복사할 바이트 수를 지정 된 `lpObject` 버퍼입니다.  
  
 `lpObject`  
 정보를 수신 하는 사용자가 제공한 버퍼를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 검색 된 바이트 수입니다. 그렇지 않으면 오류가 있는 경우 0이 발생합니다.  
  
### <a name="remarks"></a>설명  
 다음 목록에 표시 된 것 처럼 함수 형식이 그래픽 개체의 유형에 따라 데이터 구조를 검색 합니다.  
  
|Object|버퍼 유형|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[비트맵](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|지원 안 함|  
  
 개체가 한 `CBitmap` 개체 `GetObject` 너비, 높이 및 비트맵의 색 형식 정보를 반환 합니다. 실제로 비트를 사용 하 여 검색할 수 [CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits)합니다.  
  
 개체가 한 `CPalette` 개체 `GetObject` 검색는 **단어** 색상표의 항목 수를 지정 하 합니다. 함수는 검색 하지 않습니다는 [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) 색상표를 정의 하는 구조입니다. 응용 프로그램 호출 하 여 표 항목에 대 한 정보를 얻을 수 [CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)합니다.  
  
##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType  
 GDI 개체 유형을 검색합니다.  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 해당 개체의 형식 그렇지 않으면 0입니다. 값은 다음 중 하나일 수 있습니다.  
  
- **OBJ_BITMAP** 비트맵  
  
- **OBJ_BRUSH** 브러시  
  
- **OBJ_FONT** 글꼴  
  
- **OBJ_PAL** 색상표  
  
- **OBJ_PEN** 펜  
  
- **OBJ_EXTPEN** 확장 펜  
  
- **OBJ_REGION** 영역  
  
- **OBJ_DC** 장치 컨텍스트  
  
- **OBJ_MEMDC** 메모리 장치 컨텍스트  
  
- **OBJ_METAFILE** 메타 파일  
  
- **OBJ_METADC** 메타 파일 장치 컨텍스트  
  
- **OBJ_ENHMETAFILE** 확장 메타 파일  
  
- **OBJ_ENHMETADC** 향상 된 메타 파일 장치 컨텍스트  
  
##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle  
 반환 `m_hObject` 하지 않는 한 **이** 은 **NULL**있으며이 경우 **NULL** 반환 됩니다.  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A `HANDLE` 연결 된 Windows GDI 개체; 그렇지 않으면 **NULL** 개체가 연결 된 경우.  
  
### <a name="remarks"></a>설명  
 일반 핸들 인터페이스 패러다임의 일부 이며 때 유용 **NULL** 핸들에 대해 유효한 또는 특수 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)합니다.  
  
##  <a name="m_hobject"></a>  CGdiObject::m_hObject  
 A `HANDLE` 포함 하는 `HBITMAP`, **HRGN**, `HBRUSH`, `HPEN`, `HPALETTE`, 또는 **HFONT** 이 개체에 연결 합니다.  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>  CGdiObject::operator! =  
 하는 경우 두 GDI 개체가 논리적으로 같지 않은지 확인 합니다.  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `obj`  
 기존에 대 한 포인터 `CGdiObject`합니다.  
  
### <a name="remarks"></a>설명  
 GDI 개체를 왼쪽에서 오른쪽에 GDI 개체와 같지 인지 여부를 확인 합니다.  
  
##  <a name="operator_eq_eq"></a>  CGdiObject::operator = =  
 두 GDI 개체가 논리적으로 동일한 지를 결정 합니다.  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `obj`  
 기존에 대 한 참조 `CGdiObject`합니다.  
  
### <a name="remarks"></a>설명  
 GDI 개체를 왼쪽에서 오른쪽에 있는 GDI 개체와 같은지 확인 합니다.  
  
##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ  
 검색 한 `HANDLE` 연결 된 Windows GDI 개체; 그렇지 않으면 **NULL** 개체가 연결 된 경우.  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject  
 브러시의 원점으로 다시 설정 하거나 논리 팔레트를 다시 설정 합니다.  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 동안 `UnrealizeObject` 의 멤버 함수는 `CGdiObject` 클래스인 것 호출할지에 대해서만 `CBrush` 또는 `CPalette` 개체입니다.  
  
 에 대 한 `CBrush` 개체 `UnrealizeObject` 시스템이 지정 된 브러시의 원점을 장치 컨텍스트로 선택 되어 다음에 다시 설정 하도록 합니다. 개체가 한 `CPalette` 개체 `UnrealizeObject` 시스템이, 이전에 실현 되지 않은 것 처럼는 팔레트를 나타내려고 하 합니다. 응용 프로그램 호출 다음에 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette) 지정된 색상표를 시스템에 대 한 함수 시스템 팔레트에 논리 팔레트를 완전히 다시 매핑합니다.  
  
 `UnrealizeObject` 스톡 개체와 함수를 사용 해야 합니다. `UnrealizeObject` 새 브러시 원점을 설정 될 때마다이 함수를 호출 합니다 (방법으로 [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg) 함수). `UnrealizeObject` 현재 선택 된 브러시 또는 모든 디스플레이 컨텍스트의 현재 선택 된 팔레트에 대 한 함수를 호출 하지 않아야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBitmap 클래스](../../mfc/reference/cbitmap-class.md)   
 [CBrush 클래스](../../mfc/reference/cbrush-class.md)   
 [CFont 클래스](../../mfc/reference/cfont-class.md)   
 [CPalette 클래스](../../mfc/reference/cpalette-class.md)   
 [CPen 클래스](../../mfc/reference/cpen-class.md)   
 [CRgn 클래스](../../mfc/reference/crgn-class.md)
