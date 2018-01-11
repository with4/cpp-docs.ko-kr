---
title: "TN039: MFC OLE 자동화 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.ole
dev_langs: C++
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18a5962c9b9254233b0990f19cdc1ff4f562d9cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE 자동화 구현
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch 인터페이스 개요  
 `IDispatch` 인터페이스는 기준인 응용 프로그램 등 Visual BASIC 또는 다른 언어와 같은 다른 응용 프로그램을 만들 수 있는 응용 프로그램의 기능을 사용 하는 속성과 메서드를 노출 하는 방법입니다. 이 인터페이스의 가장 중요 한 부분은 **idispatch:: Invoke** 함수입니다. MFC 사용 "디스패치 맵" 구현 하려면 **idispatch:: Invoke**합니다. 디스패치 맵 레이아웃에 "shape"의 MFC 구현 정보를 제공 하면 `CCmdTarget`-파생 된 클래스를 직접 개체의 속성을 조작 하거나 멤버를 만족 하는 개체 내에서 함수 호출 수 있도록  **Idispatch:: Invoke** 요청 합니다.  
  
 대부분의 경우 클래스 마법사 및 MFC 대부분의 응용 프로그램 프로그래머에서 OLE 자동화의 상세 정보를 숨길 수 있도록 협력 합니다. 프로그래머는 응용 프로그램에 노출 하도록 실제 기능에 중점을 두기 및 기본 내부 작업에 걱정할 필요가 없습니다.  
  
 그러나 MFC 수행 하는 원리를 자세히 파악할수록을 이해 해야 하는 경우가 있습니다. 이 노트 프레임 워크 할당 하는 방법을 다룰 **DISPID**멤버 함수 및 속성에 s 합니다. MFC 할당 하는 데 사용 하 여 알고리즘의 기술 **DISPID**응용 프로그램의 개체에 대 한 "형식 라이브러리"를 만들 때와 같은 Id를 알 필요가 s는만 필요 합니다.  
  
## <a name="mfc-dispid-assignment"></a>MFC DISPID 할당  
 실제 이름 (Visual Basic 사용자, 예:), 자동화의 최종 사용자에 게 표시 되지만 자동화 사용 (예: obj. 코드의 속성 및 메서드 설정 ShowWindow)의 구현 **idispatch:: Invoke** 실제 이름을 수신 하지 않습니다. 수신 최적화의 이유로 한 **DISPID**, 32 비트 "매직 쿠키" 메서드 또는 속성에 액세스 하는 설명 하는 합니다. 이러한 **DISPID** 에서 값이 반환 된 `IDispatch` 라는 다른 메서드를 통해 구현 **IDispatch::GetIDsOfNames**합니다. 자동화 클라이언트 응용 프로그램에서 호출할 `GetIDsOfNames` 를 액세스, 이후 호출을 위해 캐시 하거나 반드시 각 멤버 또는 속성에 대 한 면 **idispatch:: Invoke**합니다. 이러한 방식으로 비용이 많이 드는 문자열 조회만 별로 한 번 개체 사용할 때마다 대신 한 번 **idispatch:: Invoke** 호출 합니다.  
  
 MFC 결정는 **DISPID**각 메서드 및 속성에 대 한 두 가지 작업에 따라:  
  
-   디스패치 맵 (1 상대적)의 위쪽에서의 거리  
  
-   디스패치 맵 가장 많이 파생 된 클래스 (상대 0)에서 거리  
  
 **DISPID** 두 부분으로 나뉘어 있습니다. **LOWORD** 의 **DISPID** 디스패치 맵 위쪽에서 거리 첫 번째 구성 요소를 포함 합니다. **HIWORD** 거리 가장 많이 파생 된 클래스를 포함 합니다. 예:  
  
```  
class CDispPoint : public CCmdTarget  
{  
public:  
    short m_x,
    m_y;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
class CDisp3DPoint : public CDispPoint  
{  
public:  
    short m_z;  
 ...  
    DECLARE_DISPATCH_MAP() 
 ...  
};  
 
BEGIN_DISPATCH_MAP(CDispPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDispPoint, "x",
    m_x,
    VT_I2)  
    DISP_PROPERTY(CDispPoint, "y",
    m_y,
    VT_I2)  
END_DISPATCH_MAP()  
 
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CDispPoint)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 볼 수 있듯이 두 클래스, OLE 자동화 인터페이스를 노출 하는 둘 다 있습니다. 이러한 클래스 중 하나에서 다른 파생 되 고 따라서 OLE 자동화 부분을 포함 하는 기본 클래스의 기능을 활용 하 여 ("x" 및 "y"이이 경우에는 속성).  
  
 MFC는 생성 **DISPID**에 대 한 클래스 CDispPoint를 다음과 같이 합니다.  
  
```  
property X    (DISPID)0x00000001  
property Y    (DISPID)0x00000002  
```  
  
 속성은 기본 클래스에 없으므로 **HIWORD** 의 **DISPID** 은 항상 0 (CDispPoint에 대 한 가장 많이 파생 된 클래스에서의 거리는 0 임).  
  
 MFC는 생성 **DISPID**에 대 한 클래스 CDisp3DPoint를 다음과 같이 합니다.  
  
```  
property Z    (DISPID)0x00000001  
property X    (DISPID)0x00010001  
property Y    (DISPID)0x00010002  
```  
  
 Z 속성 제공할지는 **DISPID** 0으로 **HIWORD** CDisp3DPoint 속성을 공개 하는 클래스에 정의 되어 있으므로 합니다. 기본 클래스에 X 및 Y 속성이 정의 되어 있으므로 **HIWORD** 의 **DISPID** 는 1, 가장 많이 파생 된 클래스에서 한 파생의 거리에는 이러한 속성은 정의 클래스입니다.  
  
> [!NOTE]
>  **LOWORD** 항상 따라 사용자가 지도에서 위치를 명시적으로 맵에 있어도 **DISPID** (에 자세한 내용은 다음 섹션을 참조는 **_ID** 버전의는 `DISP_PROPERTY` 및 `DISP_FUNCTION` 매크로).  
  
## <a name="advanced-mfc-dispatch-map-features"></a>고급 MFC 디스패치 맵 기능  
 이 버전의 Visual c + + 클래스 마법사 지원 하지 않는 추가 기능의 여러 가지가 있습니다. 클래스 마법사 지원 `DISP_FUNCTION`, `DISP_PROPERTY`, 및 `DISP_PROPERTY_EX` 을 정의 하는 메서드, 멤버 변수 속성 및 get/set 멤버 함수 속성을 각각. 이러한 기능은 대부분 자동화 서버를 만드는 데는 일반적으로 합니다.  
  
 지원 되는 클래스 마법사 매크로 적합 하지 않을 때 다음 추가 매크로 사용할 수 있습니다: `DISP_PROPERTY_NOTIFY`, 및 `DISP_PROPERTY_PARAM`합니다.  
  
## <a name="disppropertynotify--macro-description"></a>DISP_PROPERTY_NOTIFY — 매크로 설명  
  
```  
 
    DISP_PROPERTY_NOTIFY(
 theClass,   
    pszName, 
    memberName, 
    pfnAfterSet, 
    vtPropType) 
```  
  
## <a name="remarks"></a>설명  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 속성의 외부 이름입니다.  
  
 `memberName`  
 속성이 저장 되기 멤버 변수의 이름입니다.  
  
 `pfnAfterSet`  
 속성이 변경 될 때 호출할 멤버 함수의 이름입니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
## <a name="remarks"></a>설명  
 이 매크로와 매우 비슷한 `DISP_PROPERTY`제외 하 고 추가 인수를 허용 합니다. 추가 인수를 *pfnAfterSet,* nothing을 반환 하 고, 'void OnPropertyNotify()' 매개 변수를 사용 하는 멤버 함수 여야 합니다. 호출 됩니다 **후** 멤버 변수를 수정 했습니다.  
  
## <a name="disppropertyparam--macro-description"></a>DISP_PROPERTY_PARAM — 매크로 설명  
  
```  
 
    DISP_PROPERTY_PARAM(
 theClass,   
    pszName, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>설명  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 속성의 외부 이름입니다.  
  
 `memberGet`  
 속성을 가져오는 사용 되는 멤버 함수의 이름입니다.  
  
 `memberSet`  
 속성을 설정 하는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
 `vtsParams`  
 공간 문자열 각 매개 변수에 대해 VTS_를 구분합니다.  
  
## <a name="remarks"></a>설명  
 과 거의 동일한는 `DISP_PROPERTY_EX` 매크로이 매크로 별도 Get 및 Set 멤버 함수를 사용 하 여 액세스 속성을 정의 합니다. 그러나이 매크로 사용 하면 속성에 대 한 매개 변수 목록을 지정할 수 있습니다. 이 다른 방법으로 매개 변수화 되거나 인덱싱된 속성을 구현 하는 데 유용 합니다. 매개 변수를 항상 겁니다 먼저 다음에 속성에 대 한 새 값. 예:  
  
```  
DISP_PROPERTY_PARAM(CMyObject, "item",
    GetItem,
    SetItem,
    VT_DISPATCH,
    VTS_I2 VTS_I2)  
```  
  
 get 및 set 멤버 함수에 해당 합니다.  
  
```  
LPDISPATCH CMyObject::GetItem(short row,
    short col)  
void CMyObject::SetItem(short row,
    short col,
    LPDISPATCH newValue)  
```  
  
## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — 매크로 설명  
  
```  
 
    DISP_FUNCTION_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnMember, 
    vtRetVal, 
    vtsParams)DISP_PROPERTY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    vtPropType)DISP_PROPERTY_NOTIFY_ID(
 theClass,   
    pszName, 
    dispid, 
    memberName, 
    pfnAfterSet, 
    vtPropType)DISP_PROPERTY_EX_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType)DISP_PROPERTY_PARAM_ID(
 theClass,   
    pszName, 
    dispid, 
    pfnGet, 
    pfnSet, 
    vtPropType, 
    vtsParams) 
```  
  
## <a name="remarks"></a>설명  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 속성의 외부 이름입니다.  
  
 `dispid`  
 메서드나 속성에 대 한 DISPID 고정된 합니다.  
  
 `pfnGet`  
 속성을 가져오는 사용 되는 멤버 함수의 이름입니다.  
  
 `pfnSet`  
 속성을 설정 하는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `memberName`  
 속성에 매핑할 멤버 변수의 이름  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
 `vtsParams`  
 공간 문자열 각 매개 변수에 대해 VTS_를 구분합니다.  
  
## <a name="remarks"></a>설명  
 이러한 매크로 사용 하면 지정 하는 **DISPID** MFC를 자동으로 하도록 하는 대신 하나를 할당 합니다. 이러한 고급 매크로 이름은 해당 ID는 매크로 이름에 추가 되는 점을 제외 하 고 (예: **DISP_PROPERTY_ID**) 및 ID 바로 뒤에 지정 된 매개 변수에 의해 결정 됩니다는 `pszName` 매개 변수입니다. AFXDISP를 참조 하십시오. 이러한 매크로 대 한 자세한 내용은 H입니다. **_ID** 항목 디스패치 맵에의 끝에 배치 해야 합니다. 자동에 영향을 줍니다 **DISPID** 동일한 방식으로 비-세대**_ID** 매크로의 버전은 (는 **DISPID**의위치에 따라 결정 됩니다). 예:  
  
```  
BEGIN_DISPATCH_MAP(CDisp3DPoint,
    CCmdTarget)  
    DISP_PROPERTY(CDisp3DPoint, "y",
    m_y,
    VT_I2)  
    DISP_PROPERTY(CDisp3DPoint, "z",
    m_z,
    VT_I2)  
    DISP_PROPERTY_ID(CDisp3DPoint, "x",
    0x00020003,
    m_x,
    VT_I2)  
END_DISPATCH_MAP()  
```  
  
 MFC는 CDisp3DPoint 클래스에 대 한 다음과 같은 Dispid을 생성 합니다.  
  
```  
property X    (DISPID)0x00020003  
property Y    (DISPID)0x00000002  
property Z     (DISPID)0x00000001  
```  
  
 지정 하는 고정 **DISPID** 유용한 방법에 기존 디스패치 인터페이스에 대 한 이전 버전과 호환성을 유지 하기 위해 특정 시스템 정의 된 메서드 또는 속성을 구현 하는 (일반적으로 음수를 가리키는  **DISPID**와 같은 **DISPID_NEWENUM** 컬렉션).  
  
#### <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>활성화에 대 한 IDispatch 인터페이스를 검색합니다.  
 많은 서버는 OLE 서버 기능과 함께 해당 문서 개체 내에서 자동화를 지원 합니다. 이 자동화 인터페이스에 대 한 액세스 권한을 얻으려면를 해야 하는 직접 액세스는 **COleClientItem::m_lpObject** 멤버 변수입니다. 아래 코드를 검색 합니다는 `IDispatch` 개체에서 파생 된 인터페이스 `COleClientItem`합니다. 이 기능은 필요한 찾을 응용 프로그램에 아래 코드를 포함할 수 있습니다.  
  
```  
LPDISPATCH CMyClientItem::GetIDispatch()  
{  
    ASSERT_VALID(this);

 ASSERT(m_lpObject != NULL);

 
    LPUNKNOWN lpUnk = m_lpObject;  
 
    Run();
*// must be running  
 
    LPOLELINK lpOleLink = NULL;  
    if (m_lpObject->QueryInterface(IID_IOleLink,   
 (LPVOID FAR*)&lpOleLink) == NOERROR)  
 {  
    ASSERT(lpOleLink != NULL);

    lpUnk = NULL;  
    if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)  
 {  
    TRACE0("Warning: Link is not connected!\n");

    lpOleLink->Release();
return NULL;  
 }  
    ASSERT(lpUnk != NULL);

 }  
 
    LPDISPATCH lpDispatch = NULL;  
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch)   
 != NOERROR)  
 {  
    TRACE0("Warning: does not support IDispatch!\n");

    return NULL;  
 }  
 
    ASSERT(lpDispatch != NULL);

    return lpDispatch;  
}  
```  
  
 디스패치 인터페이스에서 반환 된이 기능을 직접 사용 하거나에 연결 된 다음 수는 `COleDispatchDriver` 형식이 안전한 액세스 합니다. 직접 사용 하는 경우 호출 하 고 있는지 확인 해당 **릴리스** 멤버 포인터를 통해 시기 (의 `COleDispatchDriver` 소멸자 기능은 기본적으로 설정).  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

