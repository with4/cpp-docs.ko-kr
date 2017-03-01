---
title: "CPen 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- HPEN
- CPen
dev_langs:
- C++
helpviewer_keywords:
- HPEN
- CPen class
- pens, MFC
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
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
ms.openlocfilehash: edea12c84a8f39161acbf367360fd86a1ff19998
ms.lasthandoff: 02/24/2017

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
|[CPen::CreatePen](#createpen)|지정 된 스타일, 두께 및 브러시 특성을 사용 하 여 논리 표면적인 또는 기하학적 펜을 만들고에 연결 된 `CPen` 개체입니다.|  
|[CPen::CreatePenIndirect](#createpenindirect)|펜 스타일, 두께 및 지정 된 색을 만드는 데는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 구조체와 연결 하는 `CPen` 개체입니다.|  
|[CPen::FromHandle](#fromhandle)|에 대 한 포인터를 반환 합니다.는 `CPen` Windows 지정 되 면 개체 `HPEN`합니다.|  
|[CPen::GetExtLogPen](#getextlogpen)|가져옵니다는 [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) 기본 구조입니다.|  
|[CPen::GetLogPen](#getlogpen)|가져옵니다는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 기본 구조입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[HPEN CPen::operator](#operator_hpen)|에 연결 된 창 핸들을 반환 된 `CPen` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여 대 한 자세한 내용은 `CPen`, 참조 [그래픽 개체](../../mfc/graphic-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecpena--cpencpen"></a><a name="cpen"></a>CPen::CPen  
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
 `nPenStyle`  
 펜 스타일을 지정합니다. 첫 번째 버전의 생성자에서이 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
- **PS_SOLID** 단색 펜을 만듭니다.  
  
- **PS_DASH** 파선된 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DOT** 점선된 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DASHDOT** 교대로 반복 되는 대시와 점이 가진 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_DASHDOTDOT** 교대로 반복 되는 대시와 이중 점이 가진 펜을 만듭니다. 펜 너비는 1 또는 더 적은, 장치 단위 하는 경우에 유효 합니다.  
  
- **PS_NULL** null 펜을 만듭니다.  
  
- **PS_INSIDEFRAME** 의 경계 사각형을 지정 하는 Windows GDI 출력 함수에 의해 생성 된 닫힌된 도형 프레임 내의 줄을 그리는 펜을 만듭니다 (예를 들어는 **타원**, **사각형**, `RoundRect`, `Pie`, 및 `Chord` 멤버 함수). 경계 사각형을 지정 하지 않는 Windows GDI 출력 함수와 함께이 스타일을 사용 하는 경우 (예를 들어는 `LineTo` 멤버 함수), 펜의 그리기 영역 프레임으로 제한 되지 않습니다.  
  
 두 번째 버전은 `CPen` 생성자 유형, 스타일, 끝 단면 및 조인 특성의 조합을 지정 합니다. 비트 OR 연산자 (|)를 사용 하 여 각 범주에서 값을 결합할 수 해야 합니다. 펜 종류는 다음 값 중 하나일 수 있습니다.  
  
- **PS_GEOMETRIC** 기하학적 펜을 만듭니다.  
  
- **PS_COSMETIC** 성형 펜을 만듭니다.  
  
     두 번째 버전은 `CPen` 다음 펜 스타일을 추가 하는 생성자 `nPenStyle`:  
  
- **PS_ALTERNATE** 다른 모든 픽셀을 설정 하는 펜을 만듭니다. (이 스타일은 표면적인 펜에만 적용할 수 있습니다.)  
  
- **PS_USERSTYLE** 사용자가 제공 하는 스타일 배열을 사용 하 여 펜을 만듭니다.  
  
     끝 캡은 다음 값 중 하나일 수 있습니다.  
  
- **PS_ENDCAP_ROUND** 끝 캡 반올림 됩니다.  
  
- **PS_ENDCAP_SQUARE** 끝 캡 사각형이 됩니다.  
  
- **PS_ENDCAP_FLAT** 끝 캡은 평면입니다.  
  
     조인 다음 값 중 하나일 수 있습니다.  
  
- **PS_JOIN_BEVEL** 조인 경사진 됩니다.  
  
- **PS_JOIN_MITER** 조인은 음으로 설정 된 현재 제한 내에서 서로 [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076) 함수입니다. 조인에는이 제한을 초과 하면, 자동으로 경사진 합니다.  
  
- **PS_JOIN_ROUND** 조인은 반올림 합니다.  
  
 `nWidth`  
 펜의 너비를 지정합니다.  
  
-   생성자의 첫 번째 버전에서이 값이 0 인 경우 너비 장치 단위는 항상 매핑 모드에 관계 없이 1 픽셀입니다.  
  
-   생성자의 두 번째 버전에 대 한 경우 `nPenStyle` 는 **PS_GEOMETRIC**, 논리 단위에 너비를 지정 합니다. 경우 `nPenStyle` 는 **PS_COSMETIC**, 너비가 1로 설정 해야 합니다.  
  
 `crColor`  
 펜의 RGB 색을 포함합니다.  
  
 `pLogBrush`  
 가리키는 `LOGBRUSH` 구조입니다. 경우 `nPenStyle` 는 **PS_COSMETIC**, `lbColor` 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조 및 `lbStyle` 의 멤버는 `LOGBRUSH` 구조로 설정 해야 **BS_SOLID**합니다. 경우 `nPenStyle` 는 **PS_GEOMETRIC**, 모든 구성원에서 펜의 브러시 특성을 지정 하는 데 사용 해야 합니다.  
  
 `nStyleCount`  
 더블 워드 단위에서 길이 지정 된 `lpStyle` 배열입니다. 이 값 이면&0; 이어야 합니다. `nPenStyle` 없는 **PS_USERSTYLE**합니다.  
  
 `lpStyle`  
 더블 워드 값의 배열 가리킵니다. 사용자 지정 스타일의 첫 번째는 대시의 길이 지정 하는 첫 번째 값, 첫 번째 공백 등과의 길이 지정 하는 두 번째 값입니다. 이 포인터가 있어야 **NULL** 경우 `nPenStyle` 없는 **PS_USERSTYLE**합니다.  
  
### <a name="remarks"></a>주의  
 인수가 없는 생성자를 사용 하는 경우 결과 초기화 해야 `CPen` 개체는 `CreatePen`, `CreatePenIndirect`, 또는 `CreateStockObject` 멤버 함수입니다.  
  
 인수를 사용 하는 생성자를 사용 하면 더 이상 없는 초기화가 필요 합니다. 인수가 없는 생성자는 항상 성공 하는 동안 오류가 발생 하는 경우 인수를 사용 하 여 생성자에서 예외를 throw 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&99;](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="a-namecreatepena--cpencreatepen"></a><a name="createpen"></a>CPen::CreatePen  
 지정 된 스타일, 두께 및 브러시 특성을 사용 하 여 논리 표면적인 또는 기하학적 펜을 만들고에 연결 된 `CPen` 개체입니다.  
  
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
 `nPenStyle`  
 펜 스타일을 지정합니다. 가능한 값의 목록에 대 한 참조는 `nPenStyle` 매개 변수는 [CPen](#cpen) 생성자입니다.  
  
 `nWidth`  
 펜의 너비를 지정합니다.  
  
-   첫 번째 버전에 대 한 `CreatePen`,이 값이 0 이면 장치 단위로 너비는 항상 매핑 모드에 관계 없이 1 픽셀입니다.  
  
-   두 번째 버전에 대 한 `CreatePen`경우 `nPenStyle` 는 **PS_GEOMETRIC**, 논리 단위에 너비를 지정 합니다. 경우 `nPenStyle` 는 **PS_COSMETIC**, 너비가 1로 설정 해야 합니다.  
  
 `crColor`  
 펜의 RGB 색을 포함합니다.  
  
 `pLogBrush`  
 가리키는 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035) 구조입니다. 경우 `nPenStyle` 는 **PS_COSMETIC**, **lbColor** 의 멤버는 `LOGBRUSH` 펜의 색을 지정 하는 구조 및 `lbStyle` 의 멤버는 `LOGBRUSH` 구조로 설정 해야 **BS_SOLID**합니다. 경우 **nPenStyle** 는 **PS_GEOMETRIC**, 모든 구성원에서 펜의 브러시 특성을 지정 하는 데 사용 해야 합니다.  
  
 `nStyleCount`  
 더블 워드 단위에서 길이 지정 된 `lpStyle` 배열입니다. 이 값 이면&0; 이어야 합니다. `nPenStyle` 없는 **PS_USERSTYLE**합니다.  
  
 `lpStyle`  
 더블 워드 값의 배열 가리킵니다. 사용자 지정 스타일의 첫 번째는 대시의 길이 지정 하는 첫 번째 값, 첫 번째 공백 등과의 길이 지정 하는 두 번째 값입니다. 이 포인터가 있어야 **NULL** 경우 `nPenStyle` 없는 **PS_USERSTYLE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면&0;이 아닌 메서드가 실패 하는 경우&0;입니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 버전의 `CreatePen` 펜으로 지정 된 스타일, 두께 및 색을 초기화 합니다. 펜 모든 장치 컨텍스트에 대 한 현재 펜으로 이후에 선택할 수 있습니다.  
  
 너비가 1 픽셀이 항상 있어야 하거나 보다 큰 펜의 **PS_NULL**, **PS_SOLID**, 또는 **PS_INSIDEFRAME** 스타일입니다.  
  
 펜 있으면는 **PS_INSIDEFRAME** 스타일과 논리 색상표에서 색이 일치 하지 않는 색 펜 디더링된 색으로 그려집니다. **PS_SOLID** 펜 스타일 디더링된 색으로 펜을 만드는 데 사용할 수 없습니다. 스타일 **PS_INSIDEFRAME** 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
 두 번째 버전의 `CreatePen` 논리적 표면적인 또는 기하학적 펜을 가진 지정 된 너비, 스타일 및/또는 특성 브러시를 초기화 합니다. 성형 펜의 너비는 항상 1입니다. 기하학적 펜의 너비는 항상 전체 단위에 지정 됩니다. 응용 프로그램 논리 펜을 만든 후 선택할 수 있습니다이 펜 장치 컨텍스트로 호출 하 여는 [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) 함수입니다. 장치 컨텍스트에 펜을 선택한 후 선과 곡선을 그리는 데 사용할 수 있습니다.  
  
-   경우 `nPenStyle` 는 **PS_COSMETIC** 및 **PS_USERSTYLE**, 항목에는 `lpStyle` 배열 스타일 단위로 대시와 공백의 길이 지정 합니다. 스타일 단위 선을 그리는 펜을 사용 하는 장치에 의해 정의 됩니다.  
  
-   경우 `nPenStyle` 는 **PS_GEOMETRIC** 및 **PS_USERSTYLE**, 항목에는 `lpStyle` 배열 논리 단위로 대시와 공백의 길이 지정 합니다.  
  
-   경우 `nPenStyle` 는 **PS_ALTERNATE**, 스타일 단위는 무시 되 고 다른 모든 픽셀을 설정 합니다.  
  
 응용 프로그램이 더 이상 필요한 경우 주어진된 펜을 호출 해야는 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) 멤버 함수 또는 파괴는 `CPen` 개체는 리소스를 더 이상 사용에서 합니다. 장치 컨텍스트에에서 펜을 선택 하면 응용 프로그램 펜을 삭제 해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&100;](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="a-namecreatepenindirecta--cpencreatepenindirect"></a><a name="createpenindirect"></a>CPen::CreatePenIndirect  
 스타일, 두께 및 가리키는 구조에 지정 된 색이 있는 펜 초기화 `lpLogPen`합니다.  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpLogPen`  
 Windows를 가리키는 [LOGPEN](../../mfc/reference/logpen-structure.md) 펜에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 너비가 1 픽셀이 항상 있어야 하거나 보다 큰 펜의 **PS_NULL**, **PS_SOLID**, 또는 **PS_INSIDEFRAME** 스타일입니다.  
  
 펜 있으면는 **PS_INSIDEFRAME** 스타일과 논리 색상표에서 색이 일치 하지 않는 색 펜 디더링된 색으로 그려집니다. **PS_INSIDEFRAME** 스타일은 동일 **PS_SOLID** 펜 굵기 1 보다 작은 경우.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&101;](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="a-namefromhandlea--cpenfromhandle"></a><a name="fromhandle"></a>CPen::FromHandle  
 에 대 한 포인터를 반환 합니다.는 `CPen` 개체는 Windows GDI pen 개체에 대 한 핸들을 지정 합니다.  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPen*  
 `HPEN`Windows GDI 펜 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CPen` 성공 하 고 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 `CPen` 개체가 핸들에 연결되지 않은 경우 임시 `CPen` 개체를 만들어 연결합니다. 이 임시 `CPen` 개체는 다음에 응용 프로그램의 경우 이벤트 루프에서 유휴 시간에, 될 때까지 모든 임시 그래픽 그 개체가 삭제 되만 유효 합니다. 즉, 임시 개체 에서만 유효 중 하나의 창 메시지를 처리 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&105;](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="a-namegetextlogpena--cpengetextlogpen"></a><a name="getextlogpen"></a>CPen::GetExtLogPen  
 가져옵니다는 **EXTLOGPEN** 기본 구조입니다.  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 `pLogPen`  
 가리키는 [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711) 펜에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 **EXTLOGPEN** 스타일, 두께 및 펜의 브러시 특성 구조를 정의 합니다. 예를 들어 호출 `GetExtLogPen` 펜의 특정 스타일과 일치 하도록 합니다.  
  
 다음 항목을 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 펜 속성에 대 한 내용은:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [EXTLOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 호출 `GetExtLogPen` 을 펜의 특성을 검색 한 다음 같은 색으로 cosmetic이 고, 새로운 펜을 만들어야 합니다.  
  
 [!code-cpp[NVC_MFCDocView #&102;](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="a-namegetlogpena--cpengetlogpen"></a><a name="getlogpen"></a>CPen::GetLogPen  
 가져옵니다는 `LOGPEN` 기본 구조입니다.  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>매개 변수  
 `pLogPen`  
 가리키는 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041) 펜에 대 한 정보를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `LOGPEN` 구조 스타일, 색 및 펜의 패턴을 정의 합니다.  
  
 예를 들어 호출 `GetLogPen` 펜의 특정 스타일과 일치 하도록 합니다.  
  
 다음 항목을 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 펜 속성에 대 한 내용은:  
  
- [GetObject](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 호출 `GetLogPen` 를 펜의 문자를 검색 한 다음 같은 색으로 단색, 새로운 펜을 만듭니다.  
  
 [!code-cpp[NVC_MFCDocView #&103;](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="a-nameoperatorhpena--cpenoperator-hpen"></a><a name="operator_hpen"></a>HPEN CPen::operator  
 연결 된 Windows GDI 핸들을 가져옵니다는 `CPen` 개체입니다.  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 Windows GDI 개체에 대 한 핸들 표현는 `CPen` 개체; 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 연산자는 직접 사용을 지원 하려면 캐스팅 연산자는 `HPEN` 개체입니다.  
  
 그래픽 개체를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [그래픽 개체](http://msdn.microsoft.com/library/windows/desktop/dd144962) 에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&104;](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CGdiObject 클래스](../../mfc/reference/cgdiobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CBrush 클래스](../../mfc/reference/cbrush-class.md)

