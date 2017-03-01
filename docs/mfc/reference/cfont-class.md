---
title: "CFont 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFont
dev_langs:
- C++
helpviewer_keywords:
- CFont class
- GDI, font classes
- fonts, MFC classes
ms.assetid: 3fad6bfe-d6ce-4ab9-967a-5ce0aa102800
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cc7ecfb850bf24013acdb55075eeb3d64d4994ee
ms.lasthandoff: 02/24/2017

---
# <a name="cfont-class"></a>CFont 클래스
Windows GDI(그래픽 장치 인터페이스) 글꼴을 캡슐화하고 글꼴 조작을 위한 멤버 함수를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CFont : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFont::CFont](#cfont)|`CFont` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CFont::CreateFont](#createfont)|초기화 한 `CFont` 에서 지정 된 특성입니다.|  
|[Cfont:: Createfontindirect](#createfontindirect)|초기화는 `CFont` 에 지정 된 특성을 가진 개체는 `LOGFONT` 구조입니다.|  
|[CFont::CreatePointFont](#createpointfont)|초기화는 `CFont` 지정한 높이와 지점과 서체의&1;/10 초 단위로 측정 합니다.|  
|[CFont::CreatePointFontIndirect](#createpointfontindirect)|동일 `CreateFontIndirect` 제외 하 고 글꼴 높이 논리 단위가 아닌 점을의&1;/10 초 단위로 측정 됩니다.|  
|[CFont::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CFont` Windows 지정 되 면 개체 **HFONT**합니다.|  
|[CFont::GetLogFont](#getlogfont)|채우기는 `LOGFONT` 에 연결 된 논리 글꼴에 대 한 정보는 `CFont` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HFONT CFont::operator](#operator_hfont)|Windows GDI 글꼴 핸들에 연결 하는 반환 된 `CFont` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여는 `CFont` 개체를 생성 한 `CFont` 개체를 사용 하 여 Windows 글꼴 연결 [CreateFont](#createfont), [CreateFontIndirect](#createfontindirect), [CreatePointFont](#createpointfont), 또는 [CreatePointFontIndirect](#createpointfontindirect), 개체의 멤버 함수를 사용 하 여 글꼴 조작 합니다.  
  
 `CreatePointFont` 및 `CreatePointFontIndirect` 함수는 보다 사용 하기 쉬우며 `CreateFont` 또는 `CreateFontIndirect` 은 변환을 수행 높이 대 한 글꼴의 포인트 크기에서 논리 단위를 자동으로 때문입니다.  
  
 대 한 자세한 내용은 `CFont`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CFont`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecfonta--cfontcfont"></a><a name="cfont"></a>CFont::CFont  
 `CFont` 개체를 생성합니다.  
  
```  
CFont();
```  
  
### <a name="remarks"></a>주의  
 결과 개체를 초기화 해야 `CreateFont`, `CreateFontIndirect`, `CreatePointFont`, 또는 `CreatePointFontIndirect` 사용할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&70;](../../mfc/codesnippet/cpp/cfont-class_1.cpp)]  
  
##  <a name="a-namecreatefonta--cfontcreatefont"></a><a name="createfont"></a>CFont::CreateFont  
 초기화는 `CFont` 지정한 특성을 가진 개체입니다.  
  
```  
BOOL CreateFont(
    int nHeight,  
    int nWidth,  
    int nEscapement,  
    int nOrientation,  
    int nWeight,  
    BYTE bItalic,  
    BYTE bUnderline,  
    BYTE cStrikeOut,  
    BYTE nCharSet,  
    BYTE nOutPrecision,  
    BYTE nClipPrecision,  
    BYTE nQuality,  
    BYTE nPitchAndFamily,  
    LPCTSTR lpszFacename);
```  
  
### <a name="parameters"></a>매개 변수  
 `nHeight`  
 원하는 높이 (논리 단위) 글꼴을 지정합니다. 참조는 `lfHeight` 의 멤버는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 대 한 설명은 합니다. 절대값 `nHeight` 변환 된 다음 장치 단위로 16, 384를 초과 하지 않아야 합니다. 요청 된 크기를 초과 하는 모든 글꼴 높이 든 모든 비교에 대 한 요청된 된 크기를 초과 하지 않는 가장 큰 글꼴이 나 가장 작은 글꼴을 글꼴 매퍼가 찾습니다.  
  
 `nWidth`  
 글꼴의 평균 너비 (논리 단위)의 문자를 지정합니다. 경우 `nWidth` 0 인 장치의 가로 세로 비율 차이의 절대 값에 따라 결정 되 고 가장 가까운 일치를 찾지를 사용할 수 있는 글꼴의 디지털화 가로 세로 비율과 일치 합니다.  
  
 `nEscapement`  
 0.1을도 단위로 escapement 벡터 및 표시 화면의 x 축 사이의 각도 지정합니다. Escapement 벡터는 줄의 첫 번째 및 마지막 문자 원본을 통해 줄입니다. 각도 x 축에서 시계 반대 방향으로 측정 됩니다. 참조는 `lfEscapement` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 자세한 내용은 합니다.  
  
 `nOrientation`  
 (0.1도 단위)에 문자의 기준선과 x 축 사이의 각도 지정합니다. 각도 y 방향이 고 y 방향을 위쪽의 좌표계에 대 한 x-축에서 시계 방향으로 좌표계에 대 한 x-축에서 시계 반대 방향으로 측정 됩니다.  
  
 `nWeight`  
 잉크가 픽셀 당 1000 단위로 글꼴 두께 지정합니다. 참조는 `lfWeight` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 에 대 한 자세한 내용은 합니다. 설명된 값은 근사값입니다. 실제 모양을 서체에 따라 달라 집니다. 일부 글꼴 사용할 `FW_NORMAL`, `FW_REGULAR`, 및 `FW_BOLD` 가중치입니다. 경우 `FW_DONTCARE` 을 지정는 기본 가중치 사용 됩니다.  
  
 `bItalic`  
 글꼴 기울임꼴인지 여부를 지정 합니다.  
  
 `bUnderline`  
 글꼴에 밑줄이 있는지 여부를 지정 합니다.  
  
 `cStrikeOut`  
 글꼴의 문자 취소선 있는지 여부를 지정 합니다. 경우 취소선 글꼴을 지정 합니다.&0;이 아닌 값으로 설정 합니다.  
  
 `nCharSet`  
 글꼴의 문자 setSee 지정는 `lfCharSet` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
 OEM 문자 집합은 시스템에 따라 다릅니다.  
  
 글꼴 다른 문자 집합을 시스템에 있을 수 있습니다. 알 수 없는 문자 집합에는 글꼴을 사용 하는 응용 프로그램 변환 또는 해당 글꼴로 렌더링 하도록 하는 문자열을 해석 하지 시도해 야 합니다. 대신, 문자열 출력 장치 드라이버에 직접 전달 되어야 합니다.  
  
 글꼴 맵 편집기를 사용 하지 않는 `DEFAULT_CHARSET` 값입니다. 응용 프로그램 이름 및 논리 글꼴을 완벽 하 게 설명 하는 글꼴의 크기를 허용 하려면이 값을 사용할 수 있습니다. 지정 된 이름의 글꼴이 없는 경우 지정된 된 글꼴에 대 한 모든 문자 집합에서 글꼴을 대체할 수 있습니다. 예기치 않은 결과 방지 하려면 응용 프로그램을 사용할지는 `DEFAULT_CHARSET` 필요한 경우에 값입니다.  
  
 `nOutPrecision`  
 원하는 출력 정밀도를 지정합니다. 출력 정밀도 출력 일치 해야 하는지, 요청된 된 글꼴의 높이, 너비, 문자 방향, 이스케이프 및 피치를 정의 합니다. 참조는 `lfOutPrecision` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값 목록과 자세한 정보에 대 한 합니다.  
  
 `nClipPrecision`  
 원하는 클리핑 정밀도 지정합니다. 클리핑 정밀도 부분적으로 클리핑 영역 외부에 있는 문자를 자르는 방법을 정의 합니다. 참조는 `lfClipPrecision` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
 포함된 된 읽기 전용 글꼴을 사용 하려면 응용 프로그램을 지정 해야 `CLIP_ENCAPSULATE`합니다.  
  
 장치, TrueType 및 벡터 글꼴의 일관 된 회전을 얻으려면 응용 프로그램 수 OR 연산자를 사용 결합 하는 `CLIP_LH_ANGLES` 값과 다른 `nClipPrecision` 값. 하는 경우는 `CLIP_LH_ANGLES` 비트가, 모든 글꼴에 대 한 회전 하는 좌표계의 방향을 왼쪽 인지에 따라 다릅니다. 오른손 또는 합니다. (참조에 대 한 설명을 좌표계의 방향에 대 한 자세한 내용은 `nOrientation` 매개 변수입니다.) 경우 `CLIP_LH_ANGLES` 은 장치 글꼴, 시계 반대 방향으로 회전 항상 설정 되지 않지만 다른 글꼴의 회전 하는 좌표계의 방향에 따라 달라 집니다.  
  
 `nQuality`  
 GDI 논리 글꼴 특성을 가지는 실제 물리적 글꼴 일치 하도록 시도해 야 신중 하 게 정의 하는 글꼴의 출력 품질을 지정 합니다. 참조는 `lfQuality` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값의 목록에 대 한 합니다.  
  
 `nPitchAndFamily`  
 폭 및 글꼴 패밀리를 지정합니다. 참조는 `lfPitchAndFamily` 멤버에는 `LOGFONT` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 값 목록과 자세한 정보에 대 한 합니다.  
  
 `lpszFacename`  
 A `CString` 또는 글꼴 서체 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 문자열의 길이 30 자를 초과할 수 없습니다. Windows [EnumFontFamilies](http://msdn.microsoft.com/library/windows/desktop/dd162619) 현재 사용할 수 있는 모든 글꼴을 열거 하는 함수를 사용할 수 있습니다. 경우 `lpszFacename` 는 `NULL`, GDI 장치 독립적인 서체를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이후에 모든 장치 컨텍스트에 대 한 글꼴의 글꼴을 선택할 수 있습니다.  
  
 `CreateFont` 함수는 새로운 Windows GDI 글꼴을 만들지 않습니다. 사용할 수 있는 실제 글꼴에서 가장 가까운 gdi의 일부를 선택만.  
  
 응용 프로그램 논리 글꼴을 만들 때 대부분의 매개 변수에 대 한 기본 설정을 사용할 수 있습니다. 특정 값 항상 지정 해야 하는 매개 변수는 `nHeight` 및 `lpszFacename`합니다. 경우 `nHeight` 및 `lpszFacename` 설정 되어 있지는 응용 프로그램에서 만든 논리 글꼴은 장치에 따라 다릅니다.  
  
 마치는 시기는 `CFont` 에서 만든 개체는 `CreateFont` 함수를 사용 하 여 `CDC::SelectObject` 장치 컨텍스트에 다른 글꼴을 선택, 삭제는 `CFont` 더 이상 필요 없는 개체.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&71;](../../mfc/codesnippet/cpp/cfont-class_2.cpp)]  
  
##  <a name="a-namecreatefontindirecta--cfontcreatefontindirect"></a><a name="createfontindirect"></a>Cfont:: Createfontindirect  
 초기화는 `CFont` 에 지정 된 특성을 가진 개체는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)구조입니다.  
  
```  
BOOL CreateFontIndirect(const LOGFONT* lpLogFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpLogFont`  
 가리키는 `LOGFONT` 논리 글꼴의 특징을 정의 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이후에 모든 장치에 대 한 현재 글꼴로 글꼴을 선택할 수 있습니다.  
  
 이 글꼴에 지정 된 특성에는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조입니다. 사용 하 여 글꼴 선택 될 때의 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 멤버 함수는 GDI 글꼴 매퍼에서 논리는 기존 물리적 글꼴 글꼴입니다. 글꼴 매퍼를 논리 글꼴에 대 한 정확히 일치 하지 못할 경우 요청된 된 특징과 가능한 한 많은 특성을 가진 일치 하는 대체 글꼴을 제공 합니다.  
  
 더 이상 필요 하지는 `CFont` 에서 만든 개체는 `CreateFontIndirect` 함수를 사용 하 여 `CDC::SelectObject` 장치 컨텍스트에 다른 글꼴을 선택, 삭제는 `CFont` 더 이상 필요 없는 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&72;](../../mfc/codesnippet/cpp/cfont-class_3.cpp)]  
  
##  <a name="a-namecreatepointfonta--cfontcreatepointfont"></a><a name="createpointfont"></a>CFont::CreatePointFont  
 이 함수는 지정 된 서체의 글꼴을 만들고 포인트 크기 하는 간단한 방법을 제공 합니다.  
  
```  
BOOL CreatePointFont(
    int nPointSize,  
    LPCTSTR lpszFaceName,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPointSize`  
 지점&1;/10 초에 글꼴 높이 요청 했습니다. (12 포인트 글꼴을 요청 하는 120 전달 예를 들어 있습니다.)  
  
 `lpszFaceName`  
 A `CString` 또는 글꼴 서체 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다. 이 문자열의 길이 30 자를 초과할 수 없습니다. Windows **EnumFontFamilies** 현재 사용할 수 있는 모든 글꼴을 열거 하는 함수를 사용할 수 있습니다. 경우 `lpszFaceName` 는 **NULL**, GDI 장치 독립적인 서체를 사용 합니다.  
  
 `pDC`  
 에 대 한 포인터는 [CDC](../../mfc/reference/cdc-class.md) 개체의 높이 변환 하는 데 사용할 `nPointSize` 논리 단위에 있습니다. 경우 **NULL**, 화면 장치 컨텍스트 변환 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 높이 자동으로 변환 `nPointSize` 논리 단위를 사용 하는 `CDC` 가리키는 개체 `pDC`합니다.  
  
 마치는 시기는 `CFont` 에서 만든 개체는 `CreatePointFont` 함수에서 먼저 장치 컨텍스트가 글꼴을 선택 하 고 삭제는 `CFont` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&73;](../../mfc/codesnippet/cpp/cfont-class_4.cpp)]  
  
##  <a name="a-namecreatepointfontindirecta--cfontcreatepointfontindirect"></a><a name="createpointfontindirect"></a>CFont::CreatePointFontIndirect  
 이 함수는 동일 [CreateFontIndirect](#createfontindirect) 점을 제외 하 고는 **lfHeight** 의 멤버는 `LOGFONT` 장치 보다는 포인트 단위의&1;/10 초에 해석 됩니다.  
  
```  
BOOL CreatePointFontIndirect(
    const LOGFONT* lpLogFont,  
    CDC* pDC = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpLogFont`  
 가리키는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 논리 글꼴의 특징을 정의 하는 구조입니다. **lfHeight** 의 멤버는 `LOGFONT` 구조 논리 단위가 아닌 점을의&1;/10 초 단위로 측정 됩니다. (예를 들어 설정 **lfHeight** 120 12 포인트 글꼴을 요청할 수 있습니다.)  
  
 `pDC`  
 에 대 한 포인터는 [CDC](../../mfc/reference/cdc-class.md) 개체의 높이 변환 하는 데 사용할 **lfHeight** 논리 단위를 합니다. 경우 **NULL**, 화면 장치 컨텍스트 변환 하는 데 사용 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에서 높이 자동으로 변환 **lfHeight** 논리 단위를 사용 하는 `CDC` 가리키는 개체 `pDC` 전달 되기 전에 `LOGFONT` 구조 Windows에 로그온 합니다.  
  
 마치는 시기는 `CFont` 에서 만든 개체는 `CreatePointFontIndirect` 함수에서 먼저 장치 컨텍스트가 글꼴을 선택 하 고 삭제는 `CFont` 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&74;](../../mfc/codesnippet/cpp/cfont-class_5.cpp)]  
  
##  <a name="a-namefromhandlea--cfontfromhandle"></a><a name="fromhandle"></a>CFont::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CFont` 지정 되 면 개체는 **HFONT** Windows GDI font 개체에 대 한 핸들입니다.  
  
```  
static CFont* PASCAL FromHandle(HFONT hFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `hFont`  
 **HFONT** Windows 글꼴에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CFont` 성공 하 고 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 하는 경우는 `CFont` 임시 핸들에 개체가 이미 연결 되지 않은 `CFont` 개체를 만들어 연결 합니다. 이 임시 `CFont` 개체는 다음에 응용 프로그램의 경우 이벤트 루프에서 유휴 시간에, 될 때까지 모든 임시 그래픽 그 개체가 삭제 되만 유효 합니다. 창 메시지를 처리 하는 동안에 해당 임시 개체가 유효한 지는 하는 또 다른 방법은 말하면 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&75;](../../mfc/codesnippet/cpp/cfont-class_6.cpp)]  
  
##  <a name="a-namegetlogfonta--cfontgetlogfont"></a><a name="getlogfont"></a>CFont::GetLogFont  
 복사본을 검색 하려면이 함수를 호출 하는 `LOGFONT` 에 대 한 구조 `CFont`합니다.  
  
```  
int GetLogFont(LOGFONT* pLogFont);
```  
  
### <a name="parameters"></a>매개 변수  
 *pLogFont*  
 에 대 한 포인터는 [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) 구조 글꼴 정보를 얻습니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 함수가 성공 하면, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&76;](../../mfc/codesnippet/cpp/cfont-class_7.cpp)]  
  
##  <a name="a-nameoperatorhfonta--cfontoperator-hfont"></a><a name="operator_hfont"></a>HFONT CFont::operator  
 이 연산자를 사용 하 여에 연결 된 글꼴의 Windows GDI 핸들을 가져올 수는 `CFont` 개체입니다.  
  
```  
operator HFONT() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows GDI font 개체의 핸들에 연결 된 `CFont` 성공 하 고 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자의 변환이 자동으로 사용 되므로 `CFont` 를 [글꼴 및 텍스트](http://msdn.microsoft.com/library/windows/desktop/dd144819)를 전달할 수 있습니다 `CFont` 개체는 함수에 **HFONT**s.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&77;](../../mfc/codesnippet/cpp/cfont-class_8.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 HIERSVR](../../visual-cpp-samples.md)   
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




