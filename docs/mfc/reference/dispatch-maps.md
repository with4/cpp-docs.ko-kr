---
title: "디스패치 맵 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- dispatch maps. macros
- dispatch maps
- dispatch map macros
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 48e5d1fe207089733caa5ed9e8ca30c2de21f95f
ms.lasthandoff: 02/24/2017

---
# <a name="dispatch-maps"></a>디스패치 맵
OLE 자동화 메서드를 호출 하 고 응용 프로그램에서 속성에 액세스 하는 방법을 제공 합니다. 이러한 요청을 디스패치를 위한 Microsoft Foundation 클래스 라이브러리에서 제공 하는 메커니즘은 디스패치 맵"," 함수 인수 및 속성 자체의 데이터 형식 뿐만 아니라 개체 기능 및 속성의 내부 및 외부 이름을 지정 하는입니다.  
  
### <a name="dispatch-maps"></a>디스패치 맵  
  
|||  
|-|-|  
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|클래스의 메서드 및 속성 (클래스 선언에 사용 해야 합니다)를 노출 하는 디스패치 맵은 사용될지를 선언 합니다.|  
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|디스패치 맵 정의 시작합니다.|  
|[END_DISPATCH_MAP](#end_dispatch_map)|디스패치 맵 정의 종료합니다.|  
|[DISP_FUNCTION](#disp_function)|디스패치 맵에서 OLE 자동화 함수를 정의 하는 데 사용 합니다.|  
|[DISP_PROPERTY](#disp_property)|OLE 자동화 속성을 정의합니다.|  
|[DISP_PROPERTY_EX](#disp_property_ex)|OLE 자동화 속성을 정의 하 고 Get 및 Set 함수 이름을 지정 합니다.|  
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|알림 사용 하 여 OLE 자동화 속성을 정의합니다.|  
|[DISP_PROPERTY_PARAM](#disp_property_param)|Get 및 Set 함수 이름과 매개 변수를 사용 하는 OLE 자동화 속성을 정의 합니다.|  
|[DISP_DEFVALUE](#disp_defvalue)|기존 속성을 개체의 기본값으로 만듭니다.|  
  
##  <a name="a-namedeclaredispatchmapa--declaredispatchmap"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP  
 하는 경우는 `CCmdTarget`-프로그램의 파생된 클래스 OLE 자동화를 지원 클래스의 메서드 및 속성을 노출 하는 디스패치 맵은 제공 해야 합니다.  
  
```   
DECLARE_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>주의  
 사용 하는 `DECLARE_DISPATCH_MAP` 클래스 선언 후에는 매크로입니다. 그런 다음는 합니다. 사용 하 여, 클래스에 대 한 멤버를 정의 하는 CPP 파일 함수는 `BEGIN_DISPATCH_MAP` 매크로입니다. 메서드 및 속성을 노출의 각 클래스에 대해 매크로 항목을 포함 합니다 ( `DISP_FUNCTION`, `DISP_PROPERTY`등). 마지막으로, 사용 된 `END_DISPATCH_MAP` 매크로입니다.  
  
> [!NOTE]
>  후 멤버를 선언 하는 경우 `DECLARE_DISPATCH_MAP`, 새 액세스 유형을 지정 해야 합니다 ( **공용**, `private`, 또는 `protected`)에 있습니다.  
  
 응용 프로그램 마법사 및 코드 마법사 자동화 클래스를 만드는 및 디스패치 맵을 유지 관리를 지원 합니다. 디스패치 맵에 대 한 자세한 내용은 참조 하십시오. [자동화 서버](../../mfc/automation-servers.md)합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCAutomation #&10;](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  

##  <a name="a-namebegindispatchmapa--begindispatchmap"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP  
 디스패치 맵 정의 선언합니다.  
  
```  
BEGIN_DISPATCH_MAP(theClass, baseClass)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 디스패치 맵은 소유 하는 클래스의 이름을 지정 합니다.  
  
 `baseClass`  
 기본 클래스 이름을 지정 `theClass`합니다.  
  
### <a name="remarks"></a>주의  
 클래스 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 디스패치 맵을 시작한는 `BEGIN_DISPATCH_MAP` 매크로 디스패치 함수 및 속성을 각각에 대해 매크로 항목을 추가 하 고 사용 하는 디스패치 맵을 완료는 `END_DISPATCH_MAP` 매크로입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  

##  <a name="a-nameenddispatchmapa--enddispatchmap"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP  
 디스패치 맵 정의 종료합니다.  
  
```   
END_DISPATCH_MAP()  
```  
  
### <a name="remarks"></a>주의  
 와 함께에서 사용 해야 `BEGIN_DISPATCH_MAP`합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h  

##  <a name="a-namedispfunctiona--dispfunction"></a><a name="disp_function"></a>DISP_FUNCTION  
 디스패치 맵에 OLE 자동화 함수를 정의합니다.  
  
```   
DISP_FUNCTION(
  theClass, 
  pszName, 
  pfnMember, 
  vtRetVal, 
  vtsParams)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 외부 함수의 이름입니다.  
  
 `pfnMember`  
 멤버 함수의 이름입니다.  
  
 `vtRetVal`  
 함수의 반환 형식을 지정 하는 값입니다.  
  
 `vtsParams`  
 함수의 매개 변수 목록을 지정 하는 하나 이상의 상수 공백으로 구분 된 목록입니다.  
  
### <a name="remarks"></a>주의  
 `vtRetVal` 형식의 인수는 **VARTYPE**합니다. 이 인수에 대 한 가능한 값은 다음과에서 가져온 것은 `VARENUM` 열거 합니다.  
  
|기호|반환 형식|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**날짜**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다. (쉼표) 공백으로 구분 하 여 이러한 값 중 하나 이상이 있는 함수의 매개 변수 목록을 지정 합니다. 예를 들면 다음과 같습니다. 
  
 [!code-cpp[NVC_MFCAutomation #&14;](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]  
  
 정수 (short)에 대 한 포인터를 올 정수 (short)를 포함 하는 목록을 지정 합니다.  
  
 **VTS_** 상수 및 그 의미는 다음과 같습니다.  
  
|기호|매개 변수 형식|  
|------------|--------------------|  
|**VTS_I2**|`Short`|  
|**VTS_I4**|`Long`|  
|**VTS_R4**|**부동 소수점**|  
|**VTS_R8**|`Double`|  
|**VTS_CY**|**const CY** 또는 **CY\***|  
|**VTS_DATE**|**날짜**|  
|**VTS_BSTR**|`LPCSTR`|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const VARIANT\* ** 또는 **VARIANT / /**|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_PI2**|**짧은\***|  
|**VTS_PI4**|**긴\***|  
|**VTS_PR4**|**부동 소수점\***|  
|**VTS_PR8**|**double\***|  
|**VTS_PCY**|**CY\***|  
|**VTS_PDATE**|**날짜\***|  
|**VTS_PBSTR**|**BSTR\***|  
|**VTS_PDISPATCH**|**LPDISPATCH\***|  
|**VTS_PSCODE**|**SCODE\***|  
|**VTS_PBOOL**|**BOOL\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_PUNKNOWN**|**LPUNKNOWN\***|  
|**VTS_NONE**|매개 변수 없이|  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

##  <a name="a-namedisppropertya--dispproperty"></a><a name="disp_property"></a>DISP_PROPERTY  
 디스패치 맵에 OLE 자동화 속성을 정의합니다.  
  
```   
DISP_PROPERTY(
  theClass, 
  pszName, 
  memberName, 
  vtPropType)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 속성의 외부 이름입니다.  
  
 `memberName`  
 속성을 저장할 멤버 변수의 이름입니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 `vtPropType` 형식의 인수는 **VARTYPE**합니다. 이 인수에 대 한 가능한 값은에서 가져온는 `VARENUM` 열거 합니다.  
  
|기호|**속성 형식**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**날짜**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 외부 클라이언트 속성을 지정 된 멤버 변수의 값을 변경 하는 경우 `memberName` 변경 변경 알림이 없습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

##  <a name="a-namedisppropertyexa--disppropertyex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX  
 OLE 자동화 속성과 이름을 가져오고 디스패치 맵에서 속성의 값을 설정 하는 데 사용 하는 함수를 정의 합니다.  
  
```   
DISP_PROPERTY_EX(
  theClass, 
  pszName, 
  memberGet, 
  memberSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 속성의 외부 이름입니다.  
  
 `memberGet`  
 속성을 가져오는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `memberSet`  
 속성을 설정 하는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 `memberGet` 및 `memberSet` 서명이 함수에 의해 결정 된 `vtPropType` 인수입니다. `memberGet` 함수 인수를 받지 않는 값을 반환 하 여 지정 된 형식의 `vtPropType`합니다. `memberSet` 하 여 지정 된 형식의 인수를 사용 하는 함수 `vtPropType` nothing을 반환 하 고 있습니다.  
  
 `vtPropType` 형식의 인수는 **VARTYPE**합니다. 이 인수에 대 한 가능한 값은에서 가져온는 `VARENUM` 열거형입니다. 이러한 값의 목록에 대 한 설명을 참조는 `vtRetVal` 매개 변수에서 [DISP_FUNCTION](#disp_function)합니다. `VT_EMPTY`에 나열 된는 `DISP_FUNCTION` remarks, 속성 데이터 형식으로 허용 되지 않습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

##  <a name="a-namedisppropertynotifya--disppropertynotify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY  
 디스패치 맵에서 알림 사용 하 여 OLE 자동화 속성을 정의합니다.  
  
```   
DISP_PROPERTY_NOTIFY(
  theClass, 
  szExternalName, 
  memberName, 
  pfnAfterSet, 
  vtPropType)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `szExternalName`  
 속성의 외부 이름입니다.  
  
 `memberName`  
 속성을 저장할 멤버 변수의 이름입니다.  
  
 `pfnAfterSet`  
 이름에 대 한 알림 함수의 `szExternalName`합니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 정의 된 속성과 달리 `DISP_PROPERTY`, 정의 된 속성 `DISP_PROPERTY_NOTIFY` 를 자동으로 호출 하 여 지정 된 함수 `pfnAfterSet` 속성이 변경 된 경우.  
  
 `vtPropType` 형식의 인수는 **VARTYPE**합니다. 이 인수에 대 한 가능한 값은에서 가져온는 `VARENUM` 열거 합니다.  
  
|기호|**속성 형식**|  
|------------|-----------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**날짜**|  
|`VT_BSTR`|`CString`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

##  <a name="a-namedisppropertyparama--disppropertyparam"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM  
 별도 액세스 속성을 정의 **가져오기** 및 `Set` 멤버 함수입니다.  
  
```   
DISP_PROPERTY_PARAM(
  theClass, 
  pszExternalName, 
  pfnGet, 
  pfnSet, 
  vtPropType,
  vtsParams)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 *pszExternalName*  
 속성의 외부 이름입니다.  
  
 `pfnGet`  
 속성을 가져오는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `pfnSet`  
 속성을 설정 하는 데 사용 되는 멤버 함수의 이름입니다.  
  
 `vtPropType`  
 속성의 형식을 지정 하는 값입니다.  
  
 `vtsParams`  
 공백으로 구분 된 문자열로 **VTS_** 가변 매개 변수 형식, 매개 변수 마다 하나씩 있습니다.  
  
### <a name="remarks"></a>주의  
 와 달리는 `DISP_PROPERTY_EX` 매크로이 매크로 사용 하면 속성에 대 한 매개 변수 목록을 지정할 수 있습니다. 인덱싱된 되거나 매개 변수화 된 속성을 구현 하기 위한 유용 합니다.  
  
### <a name="example"></a>예제  
 Get 다음 선언을 고려 하십시오 및 멤버 속성에 액세스 하는 경우 특정 행 및 열을 요청 하는 데 사용할 수 있는 기능을 설정 합니다.  
  
 [!code-cpp[NVC_MFCActiveXControl #&9;](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]  
  
 이 값은 다음 `DISP_PROPERTY_PARAM` 컨트롤 디스패치 맵 매크로:  
  
 [!code-cpp[NVC_MFCActiveXControl #&10;](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]  
  
 또 다른 예로, 다음 get을 고려 하 고 set 멤버 함수:  
  
 [!code-cpp[NVC_MFCActiveXControl #&11;](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]  
  
 이 값은 다음 `DISP_PROPERTY_PARAM` 컨트롤 디스패치 맵 매크로:  
  
 [!code-cpp[NVC_MFCActiveXControl #&12;](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

##  <a name="a-namedispdefvaluea--dispdefvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE  
 기존 속성을 개체의 기본값으로 만듭니다.  
  
```   
DISP_DEFVALUE(theClass, pszName)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 클래스의 이름입니다.  
  
 `pszName`  
 개체의 "값"을 나타내는 속성의 외부 이름입니다.  
  
### <a name="remarks"></a>주의  
 기본값을 사용하면 Visual Basic 응용 프로그램에 대한 자동화 개체 프로그래밍을 더 간소화할 수 있습니다.  
  
 개체의 "기본값"은 개체에 대한 참조가 속성 또는 멤버 함수를 지정하지 않을 때 검색 또는 설정되는 속성입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdisp.h 

## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

