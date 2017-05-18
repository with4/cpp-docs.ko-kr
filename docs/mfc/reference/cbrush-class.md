---
title: "CBrush 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
dev_langs:
- C++
helpviewer_keywords:
- brushes, CBrush class
- CBrush class
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
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
ms.openlocfilehash: efcbe2757de3a7e4621e2b20c88726ead111cf8c
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cbrush-class"></a>CBrush 클래스
Windows GDI(그래픽 장치 인터페이스) 브러시를 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CBrush : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBrush::CBrush](#cbrush)|`CBrush` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBrush::CreateBrushIndirect](#createbrushindirect)|스타일, 색 및 패턴에 지정 된 브러시를 초기화 한 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조입니다.|  
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|장치 독립적 비트맵 (DIB)로 지정 된 패턴으로는 브러시를 초기화 합니다.|  
|[CBrush::CreateHatchBrush](#createhatchbrush)|지정 된 교차 무늬 패턴 및 색 브러시를 초기화합니다.|  
|[CBrush::CreatePatternBrush](#createpatternbrush)|비트맵으로 지정 된 패턴으로는 브러시를 초기화 합니다.|  
|[CBrush::CreateSolidBrush](#createsolidbrush)|지정 된 단색으로 브러시를 초기화합니다.|  
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|기본 시스템 색상 브러시를 만듭니다.|  
|[CBrush::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CBrush` Windows에 대 한 핸들을 지정 하는 경우 개체 `HBRUSH` 개체입니다.|  
|[CBrush::GetLogBrush](#getlogbrush)|가져옵니다는 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HBRUSH CBrush::operator](#operator_hbrush)|에 연결 된 창 핸들을 반환 된 `CBrush` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 사용 하는 `CBrush` 개체를 생성 한 `CBrush` 개체를 하나 전달 `CDC` 브러시를 필요로 하는 멤버 함수입니다.  
  
 무늬, 또는 무늬 브러시 실선, 가능 합니다.  
  
 대 한 자세한 내용은 `CBrush`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CBrush`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cbrush"></a>CBrush::CBrush  
 `CBrush` 개체를 생성합니다.  
  
```  
CBrush(); 
CBrush(COLORREF crColor); 
CBrush(int nIndex, COLORREF crColor); 
explicit CBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `crColor`  
 RGB 색으로 브러시의 전경색을 지정합니다. 브러시 무늬는 경우이 매개 변수는 빗살 무늬의 색을 지정 합니다.  
  
 `nIndex`  
 브러시의 해치 스타일을 지정합니다. 다음 값 중 하나를 수 있습니다.  
  
- `HS_BDIAGONAL`45도 회전 하향 해치 (왼쪽에서 오른쪽)  
  
- `HS_CROSS`가로 및 세로 격자  
  
- `HS_DIAGCROSS`45도 교차 무늬  
  
- `HS_FDIAGONAL`45도 회전 상향 해치 (왼쪽에서 오른쪽)  
  
- `HS_HORIZONTAL`가로 빗살 무늬  
  
- `HS_VERTICAL`세로 빗살 무늬  
  
 `pBitmap`  
 가리키는 `CBitmap` 브러시를 칠하는 있는 비트맵을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 `CBrush`가&4; 개의 오버 로드 생성자입니다. 인수가 없는 생성자가 초기화 되지 않은 생성 `CBrush` 개체를 사용 하려면 먼저 초기화 해야 합니다.  
  
 인수가 없는 생성자를 사용 하는 경우 결과 초기화 해야 `CBrush` 개체 [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), 또는 [CreateDIBPatternBrush](#createdibpatternbrush)합니다. 인수를 사용 하는 생성자 중 하나를 사용 하는 경우 다음 더 이상 초기화가 필요 합니다. 인수가 있는 생성자는 인수가 없는 생성자는 항상 성공 하는 동안 오류가 발생 하는 경우 예외를 throw 수 있습니다.  
  
 단일 생성자 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 매개 변수는 지정 된 색으로 단색 브러시를 생성 합니다. 색을 RGB 값을 지정 하 고으로 생성할 수 있습니다는 `RGB` WINDOWS에는 매크로입니다.&8;.  
  
 두 개의 매개 변수를 사용 하 여 생성자 빗살 무늬 브러시를 생성합니다. `nIndex` 빗살 무늬로의 인덱스를 지정 하는 매개 변수입니다. `crColor` 매개 변수는 색을 지정 합니다.  
  
 포함 된 생성자는 `CBitmap` 매개 변수는 무늬 브러시를 생성 합니다. 매개 변수는 비트맵을 식별합니다. 비트맵을 사용 하 여 만들어진 것으로 가정 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), 또는 [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap)합니다. 채우기 패턴에 사용할 비트맵에 대 한 최소 크기는 8 x 8 픽셀입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&21;](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]  
  
##  <a name="createbrushindirect"></a>CBrush::CreateBrushIndirect  
 스타일, 색 및 패턴에 지정 된 브러시를 초기화 한 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조입니다.  
  
```  
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpLogBrush*  
 가리키는 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 브러시에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 모든 장치 컨텍스트에 대 한 현재 브러시로 선택할 이후에 브러시를 사용할 수 있습니다.  
  
 (평면 1, 픽셀당 1 비트)의 흑백 비트맵을 사용 하 여 만든 브러시는 현재 텍스트 색과 배경색을 사용 하 여 그려집니다. 0으로 설정 하는 비트를 나타내는 픽셀 현재 텍스트 색으로 그려집니다. 1로 설정 하는 비트를 나타내는 픽셀을 현재 배경색으로 그려집니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&22;](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]  
  
##  <a name="createdibpatternbrush"></a>CBrush::CreateDIBPatternBrush  
 장치 독립적 비트맵 (DIB)로 지정 된 패턴으로는 브러시를 초기화 합니다.  
  
```  
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,  
    UINT nUsage);

 
BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,  
    UINT nUsage);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPackedDIB*  
 압축 된 장치 독립적 비트맵 DIB ()를 포함 하는 전역 메모리 개체를 식별 합니다.  
  
 *nUsage*  
 지정 여부는 **bmiColors** 의 필드는 [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) 현재 실현된 논리 색상표에 명시적 RGB 값 또는 인덱스를 포함 하는 데이터 구조 ("압축 DIB"의 일부). 매개 변수는 다음 값 중 하나 여야 합니다.  
  
- **DIB_PAL_COLORS** 색상표 16 비트 인덱스의 배열로 구성 됩니다.  
  
- **DIB_RGB_COLORS** 색상표 리터럴 RGB 값을 포함 합니다.  
  
 *lpPackedDIB*  
 구성 된 압축된 DIB 가리키는 `BITMAPINFO` 구조 바로 뒤에 비트맵의 픽셀을 정의 하는 바이트 배열입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 브러시는 래스터 작업을 지 원하는 모든 장치 컨텍스트에 대 한 이후에 선택할 수 있습니다.  
  
 두 버전에는 DIB를 처리 하는 방식과 다릅니다.  
  
-   첫 번째 버전에는 DIB에 핸들을 얻기 위해 호출 Windows **GlobalAlloc** 함수를 전역 메모리 블록을 할당 하 고 다음 메모리에 압축 된 DIB을 채웁니다.  
  
-   두 번째 버전에서는 필요 없는 호출 **GlobalAlloc** 압축된 DIB에 메모리를 할당 합니다.  
  
 압축 된 DIB 이루어져는 `BITMAPINFO` 바로 뒤에 비트맵의 픽셀을 정의 하는 바이트 배열 데이터 구조입니다. 채우기 패턴으로 사용 하는 비트맵 8 x 8 픽셀 이어야 합니다. 비트맵 크기가 큰 경우, Windows는 처음 8 개 행 및 비트맵의 왼쪽 위 모퉁이 있는 픽셀의 8 개의 열에 해당 하는 비트를 사용 하 여 채우기 패턴을 만듭니다.  
  
 흑백 장치 컨텍스트에서 두 가지 색 DIB 패턴 브러시를 선택 하는 응용 프로그램, Windows는 DIB에 지정 된 색 무시 하 고 대신 장치 컨텍스트의 현재 텍스트와 배경 색을 사용 하는 패턴 브러시를 표시 합니다. 픽셀 DIB (오프셋에서 DIB 색상표에서)의 첫 번째 색에 매핑된 텍스트 색을 사용 하 여 표시 됩니다. 오프셋 1 색상표) (에서 두 번째 색에 매핑된 픽셀 배경색을 사용 하 여 표시 됩니다.  
  
 다음 Windows 기능 사용에 대 한 정보를 참조 하십시오.는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]:  
  
- [CreateDIBPatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183492) (이 함수는 3.0 이전 버전의 Windows 용으로 작성 된 응용 프로그램 호환성을 위해서만 제공 됩니다; 사용 된 **CreateDIBPatternBrushPt** 함수입니다.)  
  
- [CreateDIBPatternBrushPt](http://msdn.microsoft.com/library/windows/desktop/dd183493) (Win32 기반 응용 프로그램에 대 한이 기능을 사용할 수 합니다.)  
  
- [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView&23;](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]  
  
##  <a name="createhatchbrush"></a>CBrush::CreateHatchBrush  
 지정 된 교차 무늬 패턴 및 색 브러시를 초기화합니다.  
  
```  
BOOL CreateHatchBrush(
    int nIndex,  
    COLORREF crColor);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 브러시의 해치 스타일을 지정합니다. 다음 값 중 하나를 수 있습니다.  
  
- `HS_BDIAGONAL`45도 회전 하향 해치 (왼쪽에서 오른쪽)  
  
- `HS_CROSS`가로 및 세로 격자  
  
- `HS_DIAGCROSS`45도 교차 무늬  
  
- `HS_FDIAGONAL`45도 회전 상향 해치 (왼쪽에서 오른쪽)  
  
- `HS_HORIZONTAL`가로 빗살 무늬  
  
- `HS_VERTICAL`세로 빗살 무늬  
  
 `crColor`  
 RGB 색 (의 해치 색)으로 브러시의 전경색을 지정합니다. 참조 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 모든 장치 컨텍스트에 대 한 현재 브러시로 선택할 이후에 브러시를 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&24;](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]  
  
##  <a name="createpatternbrush"></a>CBrush::CreatePatternBrush  
 비트맵으로 지정 된 패턴으로는 브러시를 초기화 합니다.  
  
```  
BOOL CreatePatternBrush(CBitmap* pBitmap);
```  
  
### <a name="parameters"></a>매개 변수  
 `pBitmap`  
 비트맵을 식별합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 브러시는 래스터 작업을 지 원하는 모든 장치 컨텍스트에 대 한 이후에 선택할 수 있습니다. 로 식별 되는 비트맵 `pBitmap` 일반적으로 사용 하 여 초기화 되는 [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap::LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), 또는 [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) 함수입니다.  
  
 채우기 패턴으로 사용 하는 비트맵 8 x 8 픽셀 이어야 합니다. 큰 비트맵 경우 해당 하는 처음 8 개 행과 열 비트맵의 왼쪽 위 모퉁이 있는 픽셀의 비트만 사용 됩니다.  
  
 관련된 비트맵 영향을 주지 않고 패턴 브러시를 삭제할 수 있습니다. 즉, 비트맵 임의 개수의 패턴 브러시를 만드는 데 사용할 수 있습니다.  
  
 흑백 비트맵 (픽셀당 1 비트, 평면 1 색)을 사용 하 여 만든 브러시는 현재 텍스트 색과 배경색을 사용 하 여 그려집니다. 0으로 설정 하는 비트를 나타내는 픽셀은 현재 텍스트 색으로 그려집니다. 1로 설정 하는 비트를 나타내는 픽셀 현재 배경색으로 그려집니다.  
  
 사용 하 여에 대 한 내용은 [CreatePatternBrush](http://msdn.microsoft.com/library/windows/desktop/dd183508)는 Windows 함수 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&25;](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]  
  
##  <a name="createsolidbrush"></a>CBrush::CreateSolidBrush  
 지정 된 단색으로 브러시를 초기화합니다.  
  
```  
BOOL CreateSolidBrush(COLORREF crColor);
```  
  
### <a name="parameters"></a>매개 변수  
 `crColor`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 브러시의 색을 지정 하는 구조입니다. 색을 RGB 값을 지정 하 고으로 생성할 수 있습니다는 `RGB` WINDOWS에는 매크로입니다.&8;.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 모든 장치 컨텍스트에 대 한 현재 브러시로 선택할 이후에 브러시를 사용할 수 있습니다.  
  
 만든 브러시를 사용 하 여 응용 프로그램이 완료할 때 `CreateSolidBrush`, 장치 컨텍스트 외부로 브러시를 선택 해야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CBrush::CBrush](#cbrush)합니다.  
  
##  <a name="createsyscolorbrush"></a>CBrush::CreateSysColorBrush  
 브러시 색을 초기화합니다.  
  
```  
BOOL CreateSysColorBrush(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 색 인덱스를 지정합니다. 이 값은 21 창 요소 중 하나를 그리는 데 사용 되는 색에 해당 합니다. 참조 [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 모든 장치 컨텍스트에 대 한 현재 브러시로 선택할 이후에 브러시를 사용할 수 있습니다.  
  
 만든 브러시를 사용 하 여 응용 프로그램이 완료할 때 `CreateSysColorBrush`, 장치 컨텍스트 외부로 브러시를 선택 해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&26;](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]  
  
##  <a name="fromhandle"></a>CBrush::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CBrush` Windows에 대 한 핸들을 지정 하는 경우 개체 [HBRUSH](#operator_hbrush) 개체입니다.  
  
```  
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `hBrush`  
 `HANDLE`에 Windows GDI 브러시입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CBrush` 성공 하 고 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CBrush` 임시 핸들에 개체가 이미 연결 되지 않은 `CBrush` 개체를 만들어 연결 합니다. 이 임시 `CBrush` 개체는 응용 프로그램의 경우 이벤트 루프에서 유휴 시간에는 다음 때만 유효 합니다. 이 이번에는 임시 그래픽 개체를 모두 삭제 됩니다. 즉, 임시 개체는 하나의 창 메시지를 처리 하는 동안에 유효 합니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CBrush::CBrush](#cbrush)합니다.  
  
##  <a name="getlogbrush"></a>CBrush::GetLogBrush  
 검색 하려면이 멤버 함수를 호출 하는 `LOGBRUSH` 구조입니다.  
  
```  
int GetLogBrush(LOGBRUSH* pLogBrush);
```  
  
### <a name="parameters"></a>매개 변수  
 `pLogBrush`  
 가리키는 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 브러시에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 및 `pLogBrush` 유효한 포인터가 반환 값은 버퍼에 저장 된 바이트 수입니다.  
  
 함수가 성공 하면 및 `pLogBrush` 는 **NULL**, 반환 값은 함수에 정보를 저장 하는 데 필요한 바이트 수가 버퍼에 저장 됩니다.  
  
 함수가 실패 한 경우 반환 값은 0입니다.  
  
### <a name="remarks"></a>주의  
 `LOGBRUSH` 구조 스타일, 색 및 브러시의 패턴을 정의 합니다.  
  
 예를 들어 호출 `GetLogBrush` 특정 색 또는 패턴 비트맵의 일치 하도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&27;](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]  
  
##  <a name="operator_hbrush"></a>HBRUSH CBrush::operator  
 이 연산자를 사용 하 여의 연결 된 Windows GDI 핸들을 가져올 수는 `CBrush` 개체입니다.  
  
```  
operator HBRUSH() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 Windows GDI 개체에 대 한 핸들 표현는 `CBrush` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자는 직접 사용을 지원 하려면 캐스팅 연산자는 `HBRUSH` 개체입니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&28;](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 PROPDLG](../../visual-cpp-samples.md)   
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBitmap 클래스](../../mfc/reference/cbitmap-class.md)   
 [CDC 클래스](../../mfc/reference/cdc-class.md)

