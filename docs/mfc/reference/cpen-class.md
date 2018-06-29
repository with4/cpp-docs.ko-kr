---
title: CPen 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17337239a3a58a0283fc96eadcd4417c3d5c69b0
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079592"
---
# <a name="cpen-class"></a>CPen 클래스
Windows GDI(그래픽 장치 인터페이스) 펜을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|`CPen` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|지정 된 스타일, 두께 및 브러시 특성을 사용 하 여 논리 형식적 또는 기하학적 펜을 만들고에 연결 된 `CPen` 개체입니다.|  
|[CPen::CreatePenIndirect](#createpenindirect)|펜 스타일, 두께 및 색에 지정 된을 만드는 데는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 구조체와에 연결 된 `CPen` 개체입니다.|  
|[CPen::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CPen` Windows 지정 되 면 개체 `HPEN`합니다.|  
|[CPen::GetExtLogPen](#getextlogpen)|가져옵니다는 [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) 구조 원본으로 사용 합니다.|  
|[CPen::GetLogPen](#getlogpen)|가져옵니다는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 구조 원본으로 사용 합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HPEN CPen::operator](#operator_hpen)|에 연결 된 Windows 핸들을 반환 된 `CPen` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여 대 한 자세한 내용은 `CPen`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cpen"></a>  CPen::CPen  
 `CPen` 개체를 생성합니다.  
  
```  
CPen();

 
CPen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
CPen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *nPenStyle*  
 펜 스타일을 지정합니다. 이 매개 변수는 생성자의 첫 번째 버전에는 다음 값 중 하나일 수 있습니다.  
  
- **PS_SOLID** 단색 펜을 만듭니다.  
  
- **PS_DASH** 파선된 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DOT** 점선된 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DASHDOT** 교대로 반복 되는 대시 및 점을 가진 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DASHDOTDOT** 교대로 반복 되는 대시와 두 개의 점이 있는 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_NULL** null 펜을 만듭니다.  
  
- **PS_INSIDEFRAME** 줄의 경계 사각형을 지정 하는 Windows GDI 출력 함수를 통해 얻은 프레임 내부를 그리는 펜을 만듭니다 (예를 들어는 `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, 및 `Chord` 멤버 함수). 이 스타일은 경계 사각형을 지정 하지 않는 Windows GDI 출력 함수와 함께 사용 하는 경우 (예를 들어는 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.  
  
 두 번째 버전은 `CPen` 생성자 유형, 스타일, 끝 단면 및 조인 특성의 조합을 지정 합니다. 비트 OR 연산자를 사용 하 여 각 범주에서 값을 ठ ा (&#124;). 펜 종류는 다음 값 중 하나일 수 있습니다.  
  
- **PS_GEOMETRIC** 기하학적 펜을 만듭니다.  
  
- **PS_COSMETIC** 성형 펜을 만듭니다.  
  
     두 번째 버전은 `CPen` 에 대 한 다음과 같은 펜 스타일을 추가 하는 생성자 *nPenStyle*:  
  
- **PS_ALTERNATE** 다른 모든 픽셀을 설정 하는 펜을 만듭니다. (이 스타일은 형식적 펜에 대해서만 적용 됩니다.)  
  
- **PS_USERSTYLE** 는 사용자가 제공한 스타일 배열을 사용 하 여 펜을 만듭니다.  
  
     끝 단면 다음 값 중 하나일 수 있습니다.  
  
- **PS_ENDCAP_ROUND** 끝 표식을 반올림 됩니다.  
  
- **PS_ENDCAP_SQUARE** 끝 표식을 사각형이 됩니다.  
  
- **PS_ENDCAP_FLAT** 끝 표식을 평면입니다.  
  
     조인 다음 값 중 하나일 수 있습니다.  
  
- **PS_JOIN_BEVEL** 조인 경사진 됩니다.  
  
- **PS_JOIN_MITER** 조인은 음으로 설정 된 현재 제한 내에 있을 때는 [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) 함수입니다. 이 제한을 초과 하는 조인, 경사진 합니다.  
  
- **PS_JOIN_ROUND** 조인은 라운드 있습니다.  
  
 *nWidth*  
 펜의 너비를 지정합니다.  
  
-   생성자의 첫 번째 버전에서이 값이 0 인 경우 너비 장치 단위는 항상 매핑 모드에 관계 없이 1 픽셀입니다.  
  
-   생성자의 두 번째 버전에 대 한 경우 *nPenStyle* 은 **PS_GEOMETRIC**, 논리 단위에 너비를 지정 합니다. 경우 *nPenStyle* 은 **PS_COSMETIC**, 너비가 1로 설정 해야 합니다.  
  
 *crColor*  
 펜 RGB 색을 포함합니다.  
  
 *pLogBrush*  
 가리키는 `LOGBRUSH` 구조입니다. 경우 *nPenStyle* 은 **PS_COSMETIC**, *lbColor* 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조와 *lbStyle*의 멤버는 `LOGBRUSH` 구조도 설정 되어 있어야 **BS_SOLID**합니다. 경우 *nPenStyle* 은 **PS_GEOMETRIC**, 모든 멤버에서 펜의 브러시 특성을 지정 하는 데 사용 해야 합니다.  
  
 *nStyleCount*  
 워드 단위 단위에서 길이 지정 된 *lpStyle* 배열입니다. 이 값 이면 0 이어야 합니다. *nPenStyle* 않습니다 **PS_USERSTYLE**합니다.  
  
 *lpStyle*  
 워드 단위 값의 배열 가리킵니다. 사용자 지정 스타일의 첫 번째 대시의 길이 지정 하는 첫 번째 값, 두 번째 값의 첫 번째 공간 및 등의 길이 지정 합니다. 이 포인터가 있어야 **NULL** 경우 *nPenStyle* 않습니다 **PS_USERSTYLE**합니다.  
  
### <a name="remarks"></a>설명  
 인수 없는 생성자를 사용 하는 경우 결과 초기화 해야 `CPen` 개체는 `CreatePen`, `CreatePenIndirect`, 또는 `CreateStockObject` 멤버 함수입니다.  
  
 인수를 사용 하는 생성자를 사용 하는 경우 없습니다 추가 초기화가 필요 합니다. 인수를 사용 하 여 생성자 인수 없는 생성자 항상 성공 하는 동안 오류가 발생 하는 경우 예외를 throw 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>  CPen::CreatePen  
 지정 된 스타일, 두께 및 브러시 특성을 사용 하 여 논리 형식적 또는 기하학적 펜을 만들고에 연결 된 `CPen` 개체입니다.  
  
```  
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *nPenStyle*  
 펜의 스타일을 지정합니다. 목록이 가능한 값에 대 한 참조는 *nPenStyle* 에서 매개 변수는 [CPen](#cpen) 생성자입니다.  
  
 *nWidth*  
 펜의 너비를 지정합니다.  
  
-   첫 번째 버전에 대 한 `CreatePen`,이 값이 0 이면 너비 장치 단위는 항상 매핑 모드에 관계 없이 1 픽셀입니다.  
  
-   두 번째 버전에 대 한 `CreatePen`경우 *nPenStyle* 은 **PS_GEOMETRIC**, 논리 단위에 너비를 지정 합니다. 경우 *nPenStyle* 은 **PS_COSMETIC**, 너비가 1로 설정 해야 합니다.  
  
 *crColor*  
 펜 RGB 색을 포함합니다.  
  
 *pLogBrush*  
 가리키는 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조입니다. 경우 *nPenStyle* 은 **PS_COSMETIC**, **lbColor** 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조와 *lbStyle*의 멤버는 `LOGBRUSH` 구조도 설정 되어 있어야 **BS_SOLID**합니다. 경우 **nPenStyle** 은 **PS_GEOMETRIC**, 모든 멤버에서 펜의 브러시 특성을 지정 하는 데 사용 해야 합니다.  
  
 *nStyleCount*  
 워드 단위 단위에서 길이 지정 된 *lpStyle* 배열입니다. 이 값 이면 0 이어야 합니다. *nPenStyle* 않습니다 **PS_USERSTYLE**합니다.  
  
 *lpStyle*  
 워드 단위 값의 배열 가리킵니다. 사용자 지정 스타일의 첫 번째 대시의 길이 지정 하는 첫 번째 값, 두 번째 값의 첫 번째 공간 및 등의 길이 지정 합니다. 이 포인터가 있어야 **NULL** 경우 *nPenStyle* 않습니다 **PS_USERSTYLE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닌 메서드가 실패 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 `CreatePen` 펜 지정 된 스타일, 두께 및 색으로를 초기화 합니다. 펜 모든 장치 컨텍스트에 대 한 현재 펜으로 이후에 선택할 수 있습니다.  
  
 1 픽셀 항상 있어야 하거나 보다 큰 너비 펜은 **PS_NULL**, **PS_SOLID**, 또는 **PS_INSIDEFRAME** 스타일입니다.  
  
 펜 있으면는 **PS_INSIDEFRAME** 스타일과 색 논리 색상표에서 색이 일치 하지 않는 펜 디더링된 색으로 그려집니다. **PS_SOLID** 펜 스타일을 디더링된 색 펜을 만드는 데 사용할 수 없습니다. 스타일 **PS_INSIDEFRAME** 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
 두 번째 버전의 `CreatePen` 논리 형식적 또는 기하학적 펜이 지정 너비, 스타일 및/또는 특성 브러시를 초기화 합니다. 성형 펜의 너비는 항상 1입니다. 기하학적 펜의 너비는 항상 전체 단위에 지정 됩니다. 응용 프로그램 논리 펜을 만든 후 선택할 수 있습니다이 펜 장치 컨텍스트로 호출 하 여는 [cdc:: selectobject](../../mfc/reference/cdc-class.md#selectobject) 함수입니다. 펜 장치 컨텍스트로 선택 된 후에 선 및 곡선을 그리는 데 사용할 수 있습니다.  
  
-   경우 *nPenStyle* 은 **PS_COSMETIC** 및 **PS_USERSTYLE**에 있는 항목의 *lpStyle* 배열 대시와 공백의에서 길이 지정 스타일 단위입니다. 스타일 단위 선을 그리는 펜을 사용 하는 장치에 의해 정의 됩니다.  
  
-   경우 *nPenStyle* 은 **PS_GEOMETRIC** 및 **PS_USERSTYLE**에 있는 항목의 *lpStyle* 배열 대시와 공백의에서 길이 지정 논리 단위입니다.  
  
-   경우 *nPenStyle* 은 **PS_ALTERNATE**, 스타일 단위는 무시 되 고 다른 모든 픽셀 설정 됩니다.  
  
 응용 프로그램에 더 이상 특정된 펜 필요를 호출 해야는 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수 또는 파괴는 `CPen` 리소스가 더 이상 사용 중입니다. 개체입니다. 장치 컨텍스트에에서 펜을 선택할 때 응용 프로그램 펜을 삭제 해야 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>  CPen::CreatePenIndirect  
 스타일, 두께 및 색에서 가리키는 구조에 있는 펜 초기화 *lpLogPen*합니다.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpLogPen*  
 Windows를 가리키는 [LOGPEN](../../mfc/reference/logpen-structure.md) 펜에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 1 픽셀 항상 있어야 하거나 보다 큰 너비 펜은 **PS_NULL**, **PS_SOLID**, 또는 **PS_INSIDEFRAME** 스타일입니다.  
  
 펜 있으면는 **PS_INSIDEFRAME** 스타일과 색 논리 색상표에서 색이 일치 하지 않는 펜 디더링된 색으로 그려집니다. **PS_INSIDEFRAME** 스타일은 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>  CPen::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CPen` 개체는 Windows GDI pen 개체에 대 한 핸들을 지정 합니다.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPen*  
 `HPEN` Windows GDI 펜에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CPen` 성공 되지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 `CPen` 개체가 핸들에 연결되지 않은 경우 임시 `CPen` 개체를 만들어 연결합니다. 이 임시 `CPen` 개체는 다음에 응용 프로그램의 경우 이벤트 루프 유휴 시간에 인 될 때까지 모든 임시 그래픽 대답 하에서 개체를 삭제만 유효 합니다. 즉, 임시 개체는 한 창 메시지를 처리 동안에 유효 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>  CPen::GetExtLogPen  
 가져옵니다는 **EXTLOGPEN** 구조 원본으로 사용 합니다.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 *pLogPen*  
 가리키는 [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) 펜에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 **EXTLOGPEN** 스타일, 두께 및 펜의 브러시 특성 구조를 정의 합니다. 예를 들어 호출 `GetExtLogPen` 펜의 특정 스타일과 일치 하도록 합니다.  
  
 펜 속성에 대 한 정보에 대 한 Windows SDK에서 다음 항목을 참조 합니다.  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 호출 `GetExtLogPen` 을 펜의 특성을 검색 한 다음 같은 색으로 외관으로 새롭게 펜을 만들어야 합니다.  
  
 [!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>  CPen::GetLogPen  
 가져옵니다는 `LOGPEN` 구조 원본으로 사용 합니다.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 *pLogPen*  
 가리키는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 펜에 대 한 정보를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 `LOGPEN` 구조 스타일, 색 및 펜의 패턴을 정의 합니다.  
  
 예를 들어 호출 `GetLogPen` 펜의 특정 스타일과 일치 하도록 합니다.  
  
 펜 속성에 대 한 정보에 대 한 Windows SDK에서 다음 항목을 참조 합니다.  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 호출 `GetLogPen` 펜의 문자를 가져오고 다음 새, 단색 펜 색으로 만듭니다.  
  
 [!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>  HPEN CPen::operator  
 연결 된 Windows GDI 핸들을 가져옵니다는 `CPen` 개체입니다.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>반환 값  
 경우 성공 Windows GDI 개체에 대 한 핸들 나타내는 `CPen` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 이 연산자는의 직접 사용을 지원 하려면 캐스팅 연산자는 `HPEN` 개체입니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 문서 참조 [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBrush 클래스](../../mfc/reference/cbrush-class.md)
