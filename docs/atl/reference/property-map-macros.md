---
title: "속성 맵 매크로 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- property maps
ms.assetid: 128bc742-2b98-4b97-a243-684dbb83db77
caps.latest.revision: 17
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: fbbed22766f9029456f15c4a554ae91322e6a275
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="property-map-macros"></a>속성 맵 매크로
이러한 매크로 속성 맵 및 항목을 정의합니다.  
  
|||  
|-|-|  
|[BEGIN_PROP_MAP](#begin_prop_map)|ATL 속성 맵에의 시작을 표시 합니다.|  
|[PROP_DATA_ENTRY](#prop_data_entry)|범위 또는 ActiveX 컨트롤의 크기를 나타냅니다.|  
|[PROP_ENTRY_TYPE](#prop_entry_type)|속성 맵의에 속성 설명, DISPID, 속성 및 속성 페이지 CLSID를 입력합니다.|  
|[PROP_ENTRY_TYPE_EX](#prop_entry_type_ex)|DISPID 속성 페이지 CLSID, 속성, 속성 설명을 입력 하 고 `IDispatch` 속성 맵에 IID입니다.|  
|[PROP_PAGE](#prop_page)|속성 맵의 속성 페이지 CLSID를 입력합니다.|  
|[END_PROP_MAP](#end_prop_map)|ATL 속성 맵의 끝을 표시 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="begin_prop_map"></a>BEGIN_PROP_MAP  
 개체의 속성 매핑이의 시작을 표시 합니다.  
  
```
BEGIN_PROP_MAP(theClass)
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 [in] 속성 맵의 포함 하는 클래스를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 속성 맵의 속성 설명, 속성 Dispid, Clsid, 속성 페이지를 저장 하 고 `IDispatch` Iid입니다. 클래스 [IPerPropertyBrowsingImpl](../../atl/reference/iperpropertybrowsingimpl-class.md), [IPersistPropertyBagImpl](../../atl/reference/ipersistpropertybagimpl-class.md), [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), 및 [ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md) 속성 맵을 사용 하 여 검색 하 고이 정보를 설정 합니다.  
  
 ATL 프로젝트 마법사는 개체를 만들 때 만들어집니다. 빈 속성 맵을 지정 하 여 `BEGIN_PROP_MAP` 뒤 [END_PROP_MAP](#end_prop_map)합니다.  
  
 `BEGIN_PROP_MAP`했을 때 없는 익스텐트 하므로 속성 맵을 사용 하 여 개체의 사용자 인터페이스를 갖고 있지 않은 속성 맵의 익스텐트 (차원) 저장 하지 않습니다. 개체가 사용자 인터페이스가 있는 ActiveX 컨트롤 인 경우 익스텐트는에 있습니다. 이 경우 지정 해야 [PROP_DATA_ENTRY](#prop_data_entry) 속성 맵의 범위를 제공 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&103;](../../atl/codesnippet/cpp/property-map-macros_1.h)]  
  
##  <a name="prop_data_entry"></a>PROP_DATA_ENTRY  
 범위 또는 ActiveX 컨트롤의 크기를 나타냅니다.  
  
```
PROP_DATA_ENTRY( szDesc, member, vt)
```    
  
### <a name="parameters"></a>매개 변수  
 `szDesc`  
 [in] 속성 설명입니다.  
  
 `member`  
 [in] 범위에 포함 된 데이터 멤버 예를 들어 `m_sizeExtent`합니다.  
  
 *vt*  
 [in] VARIANT 형식의 속성을 지정합니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하면 지정된 된 데이터 멤버를 유지 합니다.  
  
 속성 맵 매크로 후 마법사에서이 매크로 삽입 ActiveX 컨트롤을 만들 때 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵 매크로 전에 [END_PROP_MAP](#end_prop_map)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 개체의 범위에서에서 ( `m_sizeExtent`)은 유지 되 고 있습니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&131;](../../atl/codesnippet/cpp/property-map-macros_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing #&132;](../../atl/codesnippet/cpp/property-map-macros_3.h)]  
  
##  <a name="prop_entry_type"></a>PROP_ENTRY_TYPE  
 이 매크로 사용 하 여 개체의 속성에 속성 설명, DISPID, 속성 및 속성 페이지 CLSID를 입력 합니다.  
  
```
PROP_ENTRY_TYPE( szDesc, dispid, clsid, vt)
```  
  
### <a name="parameters"></a>매개 변수  
 `szDesc`  
 [in] 속성 설명입니다.  
  
 `dispid`  
 [in] 속성의 DISPID 합니다.  
  
 `clsid`  
 [in] 연결된 속성 페이지의 CLSID입니다. 특수 값을 사용 하 여 `CLSID_NULL` 관련된 속성 페이지를 하지 않은 속성에 대 한 합니다.  
  
 `vt`  
 [in] 속성의 형식입니다.  
  
### <a name="remarks"></a>주의  
 `PROP_ENTRY` 매크로 안전 하 고 사용 되지 않는 합니다. 으로 대체 되었습니다 `PROP_ENTRY_TYPE`합니다.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵의의 시작을 표시 하는 매크로 이며, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [BEGIN_PROP_MAP](#begin_prop_map)합니다.  
  
##  <a name="prop_entry_type_ex"></a>PROP_ENTRY_TYPE_EX  
 유사한 [PROP_ENTRY_TYPE](#prop_entry_type), 개체가 여러 개의 이중 인터페이스를 지 원하는 경우 특정 IID를 지정할 수 있습니다.  
  
```
PROP_ENTRY_TYPE_EX( szDesc, dispid, clsid, iidDispatch, vt)
```    
  
### <a name="parameters"></a>매개 변수  
 `szDesc`  
 [in] 속성 설명입니다.  
  
 `dispid`  
 [in] 속성의 DISPID 합니다.  
  
 `clsid`  
 [in] 연결된 속성 페이지의 CLSID입니다. 특수 값을 사용 하 여 `CLSID_NULL` 관련된 속성 페이지를 하지 않은 속성에 대 한 합니다.  
  
 `iidDispatch`  
 [in] 속성을 정의 하는 이중 인터페이스의 IID입니다.  
  
 `vt`  
 [in] 속성의 형식입니다.  
  
### <a name="remarks"></a>주의  
 `PROP_ENTRY_EX` 매크로 안전 하 고 사용 되지 않는 합니다. 으로 대체 되었습니다 `PROP_ENTRY_TYPE_EX`합니다.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵의의 시작을 표시 하는 매크로 이며, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 그룹에 대 한 항목 `IMyDual1` 에 대 한 항목이 옵니다 `IMyDual2`합니다. 이중 인터페이스로 그룹화 하 여 성능이 향상 됩니다.  
  
 [!code-cpp[NVC_ATL_Windowing #&133;](../../atl/codesnippet/cpp/property-map-macros_4.h)]  
  
##  <a name="prop_page"></a>PROP_PAGE  
 이 매크로 사용 하 여 개체의 속성 맵의 속성 페이지 CLSID를 입력 합니다.  
  
```
PROP_PAGE(clsid)
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 속성 페이지의 CLSID입니다.  
  
### <a name="remarks"></a>주의  
 `PROP_PAGE`유사한 [PROP_ENTRY_TYPE](#prop_entry_type), 하지만 속성 설명 또는 DISPID 필요 하지 않습니다.  
  
> [!NOTE]
>  인 CLSID를 이미 시작한 경우 `PROP_ENTRY_TYPE` 또는 [PROP_ENTRY_TYPE_EX](#prop_entry_type_ex), 추가 항목을 만들 필요가 없습니다 `PROP_PAGE`합니다.  
  
 [BEGIN_PROP_MAP](#begin_prop_map) 속성 맵의의 시작을 표시 하는 매크로 이며, [END_PROP_MAP](#end_prop_map) 매크로 끝을 표시 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&134;](../../atl/codesnippet/cpp/property-map-macros_5.h)]  
  
##  <a name="end_prop_map"></a>END_PROP_MAP  
 개체의 속성 매핑이의 끝을 표시 합니다.  
  
```
END_PROP_MAP()
```  
  
### <a name="remarks"></a>주의  
 ATL 프로젝트 마법사는 개체를 만들 때 만들어집니다. 빈 속성 맵을 지정 하 여 [BEGIN_PROP_MAP](#begin_prop_map) 뒤 `END_PROP_MAP`합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [BEGIN_PROP_MAP](#begin_prop_map)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)

