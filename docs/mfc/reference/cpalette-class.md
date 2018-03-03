---
title: "CPalette 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPalette
- AFXWIN/CPalette
- AFXWIN/CPalette::CPalette
- AFXWIN/CPalette::AnimatePalette
- AFXWIN/CPalette::CreateHalftonePalette
- AFXWIN/CPalette::CreatePalette
- AFXWIN/CPalette::FromHandle
- AFXWIN/CPalette::GetEntryCount
- AFXWIN/CPalette::GetNearestPaletteIndex
- AFXWIN/CPalette::GetPaletteEntries
- AFXWIN/CPalette::ResizePalette
- AFXWIN/CPalette::SetPaletteEntries
dev_langs:
- C++
helpviewer_keywords:
- CPalette [MFC], CPalette
- CPalette [MFC], AnimatePalette
- CPalette [MFC], CreateHalftonePalette
- CPalette [MFC], CreatePalette
- CPalette [MFC], FromHandle
- CPalette [MFC], GetEntryCount
- CPalette [MFC], GetNearestPaletteIndex
- CPalette [MFC], GetPaletteEntries
- CPalette [MFC], ResizePalette
- CPalette [MFC], SetPaletteEntries
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 486338d579f304a6de1a54674a7711bb6c56f38c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cpalette-class"></a>CPalette 클래스
Windows 색상표를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPalette : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPalette::CPalette](#cpalette)|생성 된 `CPalette` 개체와 연결 된 Windows 색상표가 합니다. 초기화 해야 합니다는 `CPalette` 사용 하려면 먼저 초기화 멤버 함수 중 하나가 지정 된 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPalette::AnimatePalette](#animatepalette)|로 식별 되는 논리 팔레트에서 항목을 대체는 `CPalette` 개체입니다. 응용 프로그램이 없는 클라이언트 영역을 업데이트 하려면 Windows 시스템 팔레트에 새 항목을 즉시 매핑되기 때문에 합니다.|  
|[CPalette::CreateHalftonePalette](#createhalftonepalette)|장치 컨텍스트에 대 한 하프톤 팔레트를 만들고 연결 하는 `CPalette` 개체입니다.|  
|[CPalette::CreatePalette](#createpalette)|Windows 색상표를 만들고이에 연결 된 `CPalette` 개체입니다.|  
|[CPalette::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CPalette` Windows 색상표 개체에 대 한 핸들을 지정 되 면 개체입니다.|  
|[CPalette::GetEntryCount](#getentrycount)|논리 팔레트 표 항목의 수를 검색 합니다.|  
|[CPalette::GetNearestPaletteIndex](#getnearestpaletteindex)|색 값을 가장 잘 맞는 논리 팔레트에서 항목의 인덱스를 반환 합니다.|  
|[CPalette::GetPaletteEntries](#getpaletteentries)|논리 팔레트 표 항목의 범위를 검색 합니다.|  
|[CPalette::ResizePalette](#resizepalette)|로 지정 된 논리 팔레트의 크기를 변경는 `CPalette` 개체 지정 된 항목 수입니다.|  
|[CPalette::SetPaletteEntries](#setpaletteentries)|논리 팔레트에 있는 항목의 범위에 RGB 색상 값 및 플래그를 설정 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HPALETTE CPalette::operator](#operator_hpalette)|반환 된 `HPALETTE` 에 연결 된는 `CPalette`합니다.|  
  
## <a name="remarks"></a>설명  
 색상표 색 출력 장치 (예: 디스플레이 장치)와 응용 프로그램 간의 인터페이스를 제공합니다. 이 인터페이스는 심각 하 게 다른 응용 프로그램에서 표시 되는 색상을 방해 하지 않고 출력 장치의 색 기능을 모두 활용 하려면 응용 프로그램을 허용 합니다. Windows 사용 되는 색을 결정 하는 응용 프로그램의 논리 팔레트 (필요한 색 목록) 및 (정의 하는 사용 가능한 색) 시스템 색상표를 사용 합니다.  
  
 A `CPalette` 개체에서 참조 하는 색상표 조작에 대 한 개체 멤버 함수를 제공 합니다. 생성 한 `CPalette` 개체를 실제 색상표 그래픽 장치 GDI (인터페이스) 개체를 만들고 해당 항목 및 기타 속성을 조작 하기 위한 멤버 함수를 사용 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CPalette`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="animatepalette"></a>CPalette::AnimatePalette  
 항목에 연결 된 논리 팔레트에서 대체는 `CPalette` 개체입니다.  
  
```  
void AnimatePalette(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartIndex`  
 애니메이션 효과를 낼 색상표의 첫 번째 항목을 지정 합니다.  
  
 `nNumEntries`  
 애니메이션 효과를 낼 색상표의 항목 수를 지정 합니다.  
  
 `lpPaletteColors`  
 배열의 첫 번째 멤버를 [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) 표 항목으로 식별 바꾸려면 구조 `nStartIndex` 및 `nNumEntries`합니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램 호출 하는 경우 `AnimatePalette`, 없기의 클라이언트 영역을 업데이트 하려면 Windows 시스템 팔레트에 새 항목을 즉시 매핑하기 때문입니다.  
  
 `AnimatePalette` 함수는 항목을 변경는 **PC_RESERVED** 플래그가 해당 설정 **palPaletteEntry** 의 멤버는 [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) 구조 에 연결 된는 `CPalette` 개체입니다. 참조 **LOGPALETTE** 이 구조에 대 한 자세한 내용은 Windows sdk입니다.  
  
##  <a name="cpalette"></a>CPalette::CPalette  
 `CPalette` 개체를 생성합니다.  
  
```  
CPalette();
```  
  
### <a name="remarks"></a>설명  
 호출 하기 전에 개체에 연결 된 색상표가 `CreatePalette` 를 하나에 연결 합니다.  
  
##  <a name="createhalftonepalette"></a>CPalette::CreateHalftonePalette  
 장치 컨텍스트에 대 한 하프톤 팔레트를 만듭니다.  
  
```  
BOOL CreateHalftonePalette(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDC`  
 장치 컨텍스트를 식별합니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 장치 컨텍스트에의 늘이기 모드로 설정 된 경우 응용 프로그램에서 하프톤 팔레트를 만들어야 **하프톤**합니다. 반환 된 논리적 하프톤 팔레트에서 [CreateHalftonePalette](http://msdn.microsoft.com/library/windows/desktop/dd183503) 멤버 함수는 다음 선택 하 고 실현 하기 전에 장치 컨텍스트로 [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) 또는 [ StretchDIBits](http://msdn.microsoft.com/library/windows/desktop/dd145121) 함수를 호출 합니다.  
  
 에 대 한 자세한 내용은 Windows SDK를 참조 하십시오. `CreateHalftonePalette` 및 **StretchDIBits**합니다.  
  
##  <a name="createpalette"></a>CPalette::CreatePalette  
 초기화 한 `CPalette` Windows 논리 색상표를 만들고에 연결 하 여 개체는 `CPalette` 개체입니다.  
  
```  
BOOL CreatePalette(LPLOGPALETTE lpLogPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpLogPalette`  
 가리키는 [LOGPALETTE](http://msdn.microsoft.com/library/windows/desktop/dd145040) 논리 팔레트에서 색에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 Windows SDK에 대 한 참조는 **LOGPALETTE** 구조입니다.  
  
##  <a name="fromhandle"></a>CPalette::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CPalette` Windows 색상표 개체에 대 한 핸들을 지정 되 면 개체입니다.  
  
```  
static CPalette* PASCAL FromHandle(HPALETTE hPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 `hPalette`  
 Windows GDI 색상표에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CPalette` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 경우는 `CPalette` 개체가 임시 Windows 팔레트에 아직 연결 되지 않은 `CPalette` 개체가 생성 되 고 연결 합니다. 이 임시 `CPalette` 개체는 다음에 응용 프로그램의 경우 이벤트 루프 유휴 시간에 인 될 때까지 모든 임시 그래픽 대답 하에서 개체를 삭제만 유효 합니다. 즉, 임시 개체는 한 창 메시지를 처리 하는 동안에 유효 합니다.  
  
##  <a name="getentrycount"></a>CPalette::GetEntryCount  
 지정 된 논리 팔레트에 있는 항목의 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetEntryCount();
```  
  
### <a name="return-value"></a>반환 값  
 논리 팔레트에 있는 항목의 수입니다.  
  
##  <a name="getnearestpaletteindex"></a>CPalette::GetNearestPaletteIndex  
 지정 된 색 값을 가장 잘 맞는 논리 팔레트에서 항목의 인덱스를 반환 합니다.  
  
```  
UINT GetNearestPaletteIndex(COLORREF crColor) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `crColor`  
 일치 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 논리 팔레트에 있는 항목의 인덱스입니다. 항목에는 거의 대부분 지정된 된 색을 동일한 색을 포함 합니다.  
  
##  <a name="getpaletteentries"></a>CPalette::GetPaletteEntries  
 논리 팔레트 표 항목의 범위를 검색 합니다.  
  
```  
UINT GetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartIndex`  
 논리 팔레트를 검색할 첫 번째 항목을 지정 합니다.  
  
 `nNumEntries`  
 논리 팔레트를 검색할 항목의 수를 지정 합니다.  
  
 `lpPaletteColors`  
 배열을 가리키는 [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) 표 항목을 수신 하도록 데이터 구조입니다. 배열에 지정 된 대로 이상의 데이터 구조에 포함 되어야 `nNumEntries`합니다.  
  
### <a name="return-value"></a>반환 값  
 논리 팔레트; 검색 된 항목의 수 함수가 실패 하는 경우 0입니다.  
  
##  <a name="operator_hpalette"></a>HPALETTE CPalette::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CPalette` 개체입니다.  
  
```  
operator HPALETTE() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우 성공 Windows GDI 개체에 대 한 핸들 나타내는 `CPalette` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는의 직접 사용을 지원 하려면 캐스팅 연산자는 `HPALETTE` 개체입니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows sdk에서입니다.  
  
##  <a name="resizepalette"></a>CPalette::ResizePalette  
 에 연결 된 논리 팔레트의 크기를 변경는 `CPalette` 개체에서 지정한 항목의 수를 `nNumEntries`합니다.  
  
```  
BOOL ResizePalette(UINT nNumEntries);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNumEntries`  
 크기가 조정 된 후에 색상표의 항목 수를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 색상표 성공적으로 크기가 조정 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램을 호출 하는 경우 `ResizePalette` 색상표의 크기를 줄이려면 크기가 조정 된 색상표에 남아 있는 항목은 변경 합니다. 응용 프로그램을 호출 하는 경우 `ResizePalette` 색상표를 확대 하려면 추가 표 항목 (빨강, 녹색 및 파랑 값은 모두 0 임) 검정색으로 설정 되 고 모든 추가 항목에 대 한 플래그는 0으로 설정 됩니다.  
  
 Windows API에 대 한 자세한 내용은 `ResizePalette`, 참조 [ResizePalette](http://msdn.microsoft.com/library/windows/desktop/dd162928) Windows sdk에서입니다.  
  
##  <a name="setpaletteentries"></a>CPalette::SetPaletteEntries  
 논리 팔레트에 있는 항목의 범위에 RGB 색상 값 및 플래그를 설정 합니다.  
  
```  
UINT SetPaletteEntries(
    UINT nStartIndex,  
    UINT nNumEntries,  
    LPPALETTEENTRY lpPaletteColors);
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartIndex`  
 설정할 논리 팔레트에 첫 번째 항목을 지정 합니다.  
  
 `nNumEntries`  
 논리 팔레트를 설정할 항목의 수를 지정 합니다.  
  
 `lpPaletteColors`  
 배열을 가리키는 [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) 표 항목을 수신 하도록 데이터 구조입니다. 배열에 지정 된 대로 이상의 데이터 구조에 포함 되어야 `nNumEntries`합니다.  
  
### <a name="return-value"></a>반환 값  
 항목 수가 설정에서 논리 팔레트; 함수가 실패 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램 호출 때 논리 팔레트 장치 컨텍스트로 선택 하는 경우 `SetPaletteEntries`, 변경 내용이 적용 되지 것입니다는 응용 프로그램 호출 될 때까지 [CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)합니다.  
  
 Windows 구조에 대 한 자세한 내용은 **PALETTEENTRY**, 참조 [PALETTEENTRY](http://msdn.microsoft.com/library/windows/desktop/dd162769) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 DIBLOOK](../../visual-cpp-samples.md)   
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](#getpaletteentries)   
 [CPalette::SetPaletteEntries](#setpaletteentries)



