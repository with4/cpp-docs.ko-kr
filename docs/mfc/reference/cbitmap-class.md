---
title: CBitmap 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
dev_langs:
- C++
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5b931c7ad4b560ce247f78dcb126f9669bceb67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cbitmap-class"></a>CBitmap 클래스
Windows GDI(그래픽 장치 인터페이스) 비트맵을 캡슐화하고 비트맵을 조작하는 멤버 함수를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBitmap : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmap::CBitmap](#cbitmap)|`CBitmap` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBitmap::CreateBitmap](#createbitmap)|지정 된 너비, 높이 및 비트 패턴이 있는 장치 종속적 메모리 비트맵을 사용 하 여 개체를 초기화 합니다.|  
|[Cbitmap:: Createbitmapindirect](#createbitmapindirect)|에 지정 된 너비, 높이 및 비트 패턴 (하나는 지정 된 경우) 사용 하 여 비트맵을 사용 하 여 개체를 초기화 한 **비트맵** 구조입니다.|  
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|지정 된 장치와 호환 되는 비트맵을 사용 하 여 개체를 초기화 합니다.|  
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|지정된 된 장치와 호환 되는 비트맵이 무시할 수 있는 개체를 초기화 합니다.|  
|[CBitmap::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CBitmap` 개체를 windows 핸들을 지정한 경우 `HBITMAP` 비트맵입니다.|  
|[CBitmap::GetBitmap](#getbitmap)|채웁니다는 **비트맵** 비트맵에 대 한 정보로 구조체입니다.|  
|[CBitmap::GetBitmapBits](#getbitmapbits)|지정된 된 버퍼에 지정 된 비트맵의 비트를 복사합니다.|  
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|비트맵의 높이 너비를 반환합니다. 높이 너비를 이전에 설정 되어 있는지로 가정 됩니다는 [SetBitmapDimension](#setbitmapdimension) 멤버 함수입니다.|  
|[CBitmap::LoadBitmap](#loadbitmap)|응용 프로그램의 실행 파일에서 명명 된 비트맵 리소스를 로드 하는 비트맵 개체에 연결 하 여 개체를 초기화 합니다.|  
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|비트맵을 로드 하 고 현재 시스템 색상을 색상을 매핑합니다.|  
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|미리 정의 된 Windows 비트맵을 로드 하는 비트맵 개체에 연결 하 여 개체를 초기화 합니다.|  
|[CBitmap::SetBitmapBits](#setbitmapbits)|지정 된 비트 값으로 비트맵의 비트를 설정합니다.|  
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|0.1 밀리미터 단위로 비트맵에 너비와 높이 할당합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HBITMAP CBitmap::operator](#operator_hbitmap)|에 연결 된 Windows 핸들을 반환 된 `CBitmap` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하는 `CBitmap` 개체, 개체를 생성, 초기화 멤버 함수 중 하나를 사용 하 여 비트맵 핸들을 연결 및 다음 개체의 멤버 함수를 호출 합니다.  
  
 와 같은 그래픽 개체를 사용 하 여 대 한 자세한 내용은 `CBitmap`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBitmap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cbitmap"></a>  CBitmap::CBitmap  
 `CBitmap` 개체를 생성합니다.  
  
```  
CBitmap();
```  
  
### <a name="remarks"></a>설명  
 초기화 멤버 함수 중 하나가 지정 된 결과 개체를 초기화 합니다.  
  
##  <a name="createbitmap"></a>  CBitmap::CreateBitmap  
 너비, 높이 및 비트 패턴이 지정되어 있는 장치 종속적 메모리 비트맵을 초기화합니다.  
  
```  
BOOL CreateBitmap(
    int nWidth,  
    int nHeight,  
    UINT nPlanes,  
    UINT nBitcount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 비트맵의 너비(픽셀)를 지정합니다.  
  
 `nHeight`  
 비트맵의 높이(픽셀)를 지정합니다.  
  
 `nPlanes`  
 비트맵에서 색 평면의 수를 지정합니다.  
  
 `nBitcount`  
 표시 픽셀당 색 비트의 수를 지정합니다.  
  
 `lpBits`  
 초기 비트맵 비트 값이 포함된 바이트 배열을 가리킵니다. **NULL**이면 새 비트맵이 초기화되어 있지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 색 비트맵에 대한 `nPlanes` 또는 `nBitcount` 매개 변수가 1로 설정되어야 합니다. 이러한 매개 변수가 둘 다 1로 설정되면 `CreateBitmap` 은 단색 비트맵을 만듭니다.  
  
 디스플레이 장치에 대 한 비트맵을 직접 선택할 수 없습니다, 있지만 선택할 수는 "메모리 장치 컨텍스트"에 대 한 현재 비트맵으로 사용 하 여 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 는 를사용하여모든호환되는장치컨텍스트에복사할[Cdc:: bitblt](../../mfc/reference/cdc-class.md#bitblt) 함수입니다.  
  
 `CBitmap` 함수에서 만들어진 `CreateBitmap` 개체 사용을 완료하면 먼저 장치 컨텍스트에서 비트맵을 선택하고 나서 `CBitmap` 개체를 삭제합니다.  
  
 자세한 내용은 **BITMAP** 구조체에서 **bmBits** 필드에 대한 설명을 참조하세요. [비트맵](../../mfc/reference/bitmap-structure.md) 구조 아래에 설명 된 [cbitmap:: Createbitmapindirect](#createbitmapindirect) 멤버 함수입니다.  
  
##  <a name="createbitmapindirect"></a>  Cbitmap:: Createbitmapindirect  
 너비, 높이 및 비트 패턴 (하나는 지정 된 경우)에서 가리키는 구조에 있는 비트맵을 초기화 합니다 `lpBitmap`합니다.  
  
```  
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpBitmap`  
 가리키는 [비트맵](../../mfc/reference/bitmap-structure.md) 비트맵에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 디스플레이 장치에 대 한 비트맵을 직접 선택할 수 없습니다, 있지만 선택할 수 있습니다 메모리 장치 컨텍스트에 대 한 현재 비트맵으로 사용 하 여 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 는 를사용하여모든호환되는장치컨텍스트에복사할[Cdc:: bitblt](../../mfc/reference/cdc-class.md#bitblt) 또는 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 함수입니다. (의 [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) 함수 디스플레이 장치 컨텍스트를 직접 현재 브러시에 대 한 비트맵을 복사할 수 있습니다.)  
  
 경우는 **비트맵** 에서 가리키는 구조는 `lpBitmap` 매개 변수를 사용 하 여 입력에 `GetObject` 함수는 비트맵의 비트를 지정 하지 않으면 및 비트맵 초기화 되지 않았습니다. 비트맵을 초기화 하려면 응용 프로그램 함수를 사용할 수와 같은 [cdc:: bitblt](../../mfc/reference/cdc-class.md#bitblt) 또는 [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) 비트의 첫 번째 매개 변수로 식별 된 비트맵에서 복사할 `CGdiObject::GetObject` 에서 만든 비트맵에 `CreateBitmapIndirect`.  
  
 사용을 완료 하면는 `CBitmap` 개체를 사용 하 여 만든 `CreateBitmapIndirect` 함수, 먼저 비트맵 장치 컨텍스트를 선택한 다음 삭제는 `CBitmap` 개체입니다.  
  
##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap  
 로 지정 된 장치에 호환 되는 비트맵을 초기화 합니다 `pDC`합니다.  
  
```  
BOOL CreateCompatibleBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 장치 컨텍스트를 지정합니다.  
  
 `nWidth`  
 비트맵의 너비(픽셀)를 지정합니다.  
  
 `nHeight`  
 비트맵의 높이(픽셀)를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 비트맵에 동일한 색상 평면 수 또는 같은 픽셀 당 비트 형식으로 지정된 된 장치 컨텍스트에 있습니다. 에 의해 지정 된 호환 되는 모든 메모리 장치에 대 한 현재 비트맵으로 선택할 수 있습니다 `pDC`합니다.  
  
 경우 `pDC` 메모리 장치 컨텍스트는 장치 컨텍스트를 반환 하는 비트맵에 같은 형식으로 현재 선택 된 비트맵입니다. "메모리 장치 컨텍스트"에 디스플레이 화면 표시 하는 메모리의 블록. 호환 장치의 실제 화면에 복사 하기 전에 메모리에 이미지를 준비 하는 사용할 수 있습니다.  
  
 자동 메모리 장치 컨텍스트를 만든 GDI에 대 한 스톡 단색 비트맵을 선택 합니다.  
  
 비트맵의 형식에서 반환 된 색 이나 선택 하는 단색 비트맵 색 메모리 장치 컨텍스트 있을 수 있지만, 이후는 `CreateCompatibleBitmap` 함수 항상 같지 않습니다; 그러나 메모리가 아닌 장치 컨텍스트에 대 한 호환 비트맵 형식을 항상는 장치의 형식입니다.  
  
 사용을 완료 하면는 `CBitmap` 사용 하 여 만든 개체는 `CreateCompatibleBitmap` 함수, 먼저 비트맵 장치 컨텍스트를 선택한 다음 삭제는 `CBitmap` 개체입니다.  
  
##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap  
 지정 된 디바이스 컨텍스트 호환 되는 무시할 수 비트맵을 초기화 합니다 `pDC`합니다.  
  
```  
BOOL CreateDiscardableBitmap(
    CDC* pDC,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 장치 컨텍스트를 지정합니다.  
  
 `nWidth`  
 비트맵의 너비 (비트) 단위로 지정합니다.  
  
 `nHeight`  
 비트맵의 높이 (bits) 단위로 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 비트맵에 동일한 색상 평면 수 또는 같은 픽셀 당 비트 형식으로 지정된 된 장치 컨텍스트에 있습니다. 응용 프로그램에 의해 지정 된 호환 되는 메모리 장치에 대 한 현재 비트맵으로이 비트맵을 선택할 수 `pDC`합니다.  
  
 Windows는 하드웨어에이 응용 프로그램에서 선택 하지 않은 경우에이 함수에 의해 만들어진 비트맵을 취소할 수 있습니다. 선택 하지 않으면 나중에 응용 프로그램을 선택 하려고 시도 하는 경우 Windows 비트맵을 삭제 하는 경우는 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 함수는 반환 **NULL**합니다.  
  
 사용을 완료 하면는 `CBitmap` 사용 하 여 만든 개체는 `CreateDiscardableBitmap` 함수, 먼저 비트맵 장치 컨텍스트를 선택한 다음 삭제는 `CBitmap` 개체입니다.  
  
##  <a name="fromhandle"></a>  CBitmap::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CBitmap` 개체 Windows GDI 비트맵에 대 한 핸들을 지정 합니다.  
  
```  
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `hBitmap`  
 Windows GDI 비트맵을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CBitmap` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CBitmap` 개체가 이미 임시 핸들에 연결 되지 않은 `CBitmap` 개체가 생성 되 고 연결 합니다. 이 임시 `CBitmap` 개체는 다음에 응용 프로그램의 경우 이벤트 루프 유휴 시간에 인 될 때까지 모든 임시 그래픽 대답 하에서 개체를 삭제만 유효 합니다. 임시 개체가 올바른지만 한 창 메시지를 처리 하는 동안는 하는 또 다른 방법은 말하면 합니다.  
  
##  <a name="getbitmap"></a>  CBitmap::GetBitmap  
 연결 된 비트맵에 대 한 이미지 속성을 검색합니다.  
  
```  
int GetBitmap(BITMAP* pBitMap);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBitMap`  
 에 대 한 포인터는 [비트맵 구조](../../mfc/reference/bitmap-structure.md) 구조를 이미지 속성이 표시 됩니다. 이 매개 변수는 `NULL`이 아니어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits  
 지정된 된 버퍼에 연결 된 비트맵의 비트 패턴을 복사합니다.  
  
```  
DWORD GetBitmapBits(
    DWORD dwCount,  
    LPVOID lpBits) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCount`  
 버퍼에 복사할 바이트 수입니다.  
  
 `lpBits`  
 비트맵 받을 버퍼에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 버퍼에 복사 된 바이트 수 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [CBitmap::GetBitmap](#getbitmap) 필요한 버퍼 크기를 결정 합니다.  
  
##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension  
 비트맵의 높이 너비를 반환합니다.  
  
```  
CSize GetBitmapDimension() const;  
```  
  
### <a name="return-value"></a>반환 값  
 비트맵의 높이 너비 (0.1 밀리미터 단위)입니다. 높이는 **cy** 의 멤버는 `CSize` 개체 및 너비는는 **cx** 멤버입니다. 비트맵의 너비와 높이 설정 하지 않은 경우 사용 하 여 경우 `SetBitmapDimension`, 반환 값은 0입니다.  
  
### <a name="remarks"></a>설명  
 높이 너비를 사용 하 여 이전에 설정한로 가정 됩니다는 [SetBitmapDimension](#setbitmapdimension) 멤버 함수입니다.  
  
##  <a name="loadbitmap"></a>  CBitmap::LoadBitmap  
 로 명명 된 비트맵 리소스 로드 `lpszResourceName` 의 ID 번호로 식별 하거나 `nIDResource` 에서 응용 프로그램의 실행 파일입니다.  
  
```  
BOOL LoadBitmap(LPCTSTR lpszResourceName);  
BOOL LoadBitmap(UINT nIDResource);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszResourceName`  
 비트맵 리소스의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `nIDResource`  
 비트맵 리소스의 리소스 ID 번호를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 로드 된 비트맵에 연결 되어는 `CBitmap` 개체입니다.  
  
 비트맵으로 식별 하는 경우 `lpszResourceName` 존재 하지 않는 또는 메모리가 부족 하 여 비트맵을 로드할 수 없으면 함수가 0을 반환 합니다.  
  
 사용할 수 있습니다는 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 비트맵을 삭제 하는 함수에 의해 로드는 `LoadBitmap` 함수 또는 `CBitmap` 소멸자를 개체를 삭제 합니다.  
  
> [!CAUTION]
>  개체를 삭제 하기 전에 장치 컨텍스트로 선택 되지 않았는지 확인 합니다.  
  
 다음과 같은 비트맵 Windows 버전 3.1 이상에 추가 되었습니다.  
  
 **OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI**  
  
 이러한 비트맵 3.0 및 이전 Windows 버전에 대 한 장치 드라이버에 제공 하지 않습니다. 비트맵 및 표시 되는 디스플레이 전체 목록을 Windows SDK를 참조 하십시오.  
  
##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap  
 현재 시스템 색상을 색상에 매핑한 비트맵을 로드 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL LoadMappedBitmap(
    UINT nIDBitmap,  
    UINT nFlags = 0,  
    LPCOLORMAP lpColorMap = NULL,  
    int nMapSize = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDBitmap`  
 비트맵 리소스의 ID입니다.  
  
 `nFlags`  
 비트맵에 대 한 플래그입니다. 0이 될 수 또는 **CMB_MASKED**합니다.  
  
 `lpColorMap`  
 에 대 한 포인터는 **COLORMAP** 비트맵을 매핑하는 데 필요한 색 정보가 포함 된 구조체입니다. 이 매개 변수가 **NULL**,이 함수는 기본 색상표를 사용 합니다.  
  
 *nMapSize*  
 가 가리키는 색 지도 수가 `lpColorMap`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `LoadMappedBitmap` 단추 문자 모양에서 일반적으로 사용 되는 색에 매핑됩니다.  
  
 매핑된 비트맵 만들기에 대 한 정보에 대 한 Windows 함수를 참조 하십시오. [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) 및 [COLORMAP](http://msdn.microsoft.com/library/windows/desktop/bb760448) Windows SDK에는 구조입니다.  
  
##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap  
 Windows에서 사용 되는 미리 정의 된 비트맵을 로드 합니다.  
  
```  
BOOL LoadOEMBitmap(UINT nIDBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDBitmap`  
 미리 정의 된 Windows 비트맵의 ID. 가능한 값은 WINDOWS에서 아래 나열 됩니다. H:  
  
|||  
|-|-|  
|**OBM_BTNCORNERS**|**OBM_OLD_RESTORE**|  
|**OBM_BTSIZE**|**OBM_OLD_RGARROW**|  
|**OBM_CHECK**|**OBM_OLD_UPARROW**|  
|**OBM_CHECKBOXES**|**OBM_OLD_ZOOM**|  
|**OBM_CLOSE**|**OBM_REDUCE**|  
|**OBM_COMBO**|**OBM_REDUCED**|  
|**OBM_DNARROW**|**OBM_RESTORE**|  
|**OBM_DNARROWD**|**OBM_RESTORED**|  
|**OBM_DNARROWI**|**OBM_RGARROW**|  
|**OBM_LFARROW**|**OBM_RGARROWD**|  
|**OBM_LFARROWD**|**OBM_RGARROWI**|  
|**OBM_LFARROWI**|**OBM_SIZE**|  
|**OBM_MNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_CLOSE**|**OBM_UPARROWD**|  
|**OBM_OLD_DNARROW**|**OBM_UPARROW**|  
|**OBM_OLD_LFARROW**|**OBM_ZOOM**|  
|**OBM_OLD_REDUCE**|**OBM_ZOOMD**|  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이름이로 시작 하는 비트맵 **OBM_OLD** 3.0 이전 Windows 버전에서 사용 하는 비트맵을 나타냅니다.  
  
 상수 **OEMRESOURCE** WINDOWS를 포함 하기 전에 정의 해야 합니다. 하나를 사용 하려면 H는 **OBM_** 상수입니다.  
  
##  <a name="operator_hbitmap"></a>  HBITMAP CBitmap::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CBitmap` 개체입니다.  
  
```  
operator HBITMAP() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우 성공 Windows GDI 개체에 대 한 핸들 나타내는 `CBitmap` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는의 직접 사용을 지원 하려면 캐스팅 연산자는 `HBITMAP` 개체입니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows sdk에서입니다.  
  
##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits  
 제공한 비트 값으로 설정 하는 비트맵의 비트 `lpBits`합니다.  
  
```  
DWORD SetBitmapBits(
    DWORD dwCount,  
    const void* lpBits);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCount`  
 가 가리키는 바이트 수가 지정 `lpBits`합니다.  
  
 `lpBits`  
 가리키는 **바이트** 배열에 복사 되도록 픽셀 값을 포함 하는 `CBitmap` 개체입니다. 비트맵 이미지를 올바르게 렌더링 수에 대 한 값을 CBitmap 인스턴스가 만들어질 때 지정 된 높이, 너비 및 색 농도 값에 맞게 포맷 해야 합니다. 자세한 내용은 참조 [CBitmap::CreateBitmap](#createbitmap)합니다.  
  
### <a name="return-value"></a>반환 값  
 비트맵 비트; 설정에 사용 된 바이트 수 함수가 실패 한 경우 0입니다.  
  
##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension  
 0.1 밀리미터 단위로 비트맵에 너비와 높이 할당합니다.  
  
```  
CSize SetBitmapDimension(
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 (0.1 밀리미터 단위)에 비트맵의 너비를 지정합니다.  
  
 `nHeight`  
 (0.1 밀리미터 단위)에 비트맵의 높이 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 비트맵 차원입니다. 높이는 **cy** 의 멤버 변수는 `CSize` 에 개체 및 너비는 **cx** 멤버 변수입니다.  
  
### <a name="remarks"></a>설명  
 GDI를 돌려보낼 응용 프로그램이 호출 하는 경우를 제외 하 고 이러한 값을 사용 하지 않는 [GetBitmapDimension](#getbitmapdimension) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)

