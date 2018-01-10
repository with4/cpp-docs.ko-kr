---
title: "범주 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
dev_langs: C++
ms.assetid: 223578cb-6180-4787-a8d8-ba3787a5d3ee
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 752a0c0c9de5c726a106ca08a574844369c6bdc5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="category-macros"></a>범주 매크로
이러한 매크로 범주 맵을 정의 합니다.  
  
|||  
|-|-|  
|[BEGIN_CATEGORY_MAP](#begin_category_map)|카테고리 맵의 시작을 표시 합니다.|  
|[END_CATEGORY_MAP](#end_category_map)|범주 맵의 끝을 표시 합니다.|  
|[IMPLEMENTED_CATEGORY](#implemented_category)|COM 개체에 의해 구현 되는 범주를 나타냅니다.|  
|[REQUIRED_CATEGORY](#required_category)|COM 개체에서 컨테이너의 필요한 범주를 나타냅니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  

##  <a name="begin_category_map"></a>BEGIN_CATEGORY_MAP  
 카테고리 맵의 시작을 표시 합니다.  
  
```
BEGIN_CATEGORY_MAP(theClass)
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 [in] 범주 맵을 포함 하는 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 카테고리 맵 COM 클래스에서 구현할 하 고 해당 컨테이너에서 필요한 범주는 구성 요소 범주를 지정 하는 데 사용 됩니다.  
  
 추가 [IMPLEMENTED_CATEGORY](#implemented_category) COM 클래스에서 구현 되는 각 범주에 대 한 지도에 입력 합니다. 추가 [REQUIRED_CATEGORY](#required_category) 클래스를 구현 하는 클라이언트에 필요한 각 범주에 대 한 지도에 입력 합니다. 지도 끝을 표시는 [END_CATEGORY_MAP](#end_category_map) 매크로입니다.  
  
 지도에 나열 된 구성 요소 범주는 자동으로 등록 모듈을 등록 하는 클래스에 연결 된 경우 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) .  
  
> [!NOTE]
>  ATL 표준 구성 요소 범주 관리자를 사용 하 여 구성 요소 범주를 등록 합니다. 없으면 관리자는 시스템에 모듈 등록 될 때, 등록 성공 하지만, 구성 요소 범주는 해당 클래스에 대해 등록 되지 않습니다.  
  
 구성 요소 범주에 대 한 자세한 내용은 참조 [무엇 구성 요소 범주 이며 어떻게 작동 합니까](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="end_category_map"></a>END_CATEGORY_MAP  
 범주 맵의 끝을 표시 합니다.  
  
```
END_CATEGORY_MAP()
```  
  
### <a name="example"></a>예  
 예를 참조 [BEGIN_CATEGORY_MAP](#begin_category_map)합니다.  
  
##  <a name="implemented_category"></a>IMPLEMENTED_CATEGORY  
 추가 `IMPLEMENTED_CATEGORY` 해당 구성 요소는 매크로 [카테고리 맵](#begin_category_map) 등록으로 식별 되는 범주를 구현 해야 함을 지정 하는 `catID` 매개 변수입니다.  
  
```
IMPLEMENTED_CATEGORY(catID)
```  
  
### <a name="parameters"></a>매개 변수  
 `catID`  
 [in] A **CATID** 상수 또는 변수 구현 된 범주에 대 한 전역 고유 식별자 (GUID)를 보유 합니다. 주소 `catID` 수행 되 고 지도에 추가 합니다. 스톡 범주 선택에 대 한 아래 표를 참조 하십시오.  
  
### <a name="remarks"></a>설명  
 지도에 나열 된 구성 요소 범주는 자동으로 등록 모듈을 등록 하는 클래스에 연결 된 경우 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로입니다.  
  
 클라이언트를 해당 형식의 인스턴스를 만들 필요 없이 해당 기능 및 요구 사항을 확인 하려면 클래스에 대해 등록 된 범주 정보를 사용할 수 있습니다.  
  
 구성 요소 범주에 대 한 자세한 내용은 참조 [무엇 구성 요소 범주 이며 어떻게 작동 합니까](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows sdk에서입니다.  
  
### <a name="a-selection-of-stock-categories"></a>스톡 범주 선택  
  
|설명|기호|레지스트리 GUID|  
|-----------------|------------|-------------------|  
|스크립팅 작업에|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|초기화에 안전 하 게 보호|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|단순 프레임 사이트 포함 항목|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|단순 데이터 바인딩|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|고급 데이터 바인딩|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|창 없는 컨트롤|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|인터넷 인식 개체|참조 [인터넷 인식 개체](http://msdn.microsoft.com/library/windows/desktop/ms690561) 샘플 목록에 대 한 Windows sdk입니다.||  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#100](../../atl/codesnippet/cpp/category-macros_1.h)]  
  
##  <a name="required_category"></a>REQUIRED_CATEGORY  
 추가 `REQUIRED_CATEGORY` 해당 구성 요소는 매크로 [카테고리 맵](#begin_category_map) 등록로 식별 되는 범주를 필요로 하는 컨트롤로 해야 함을 지정 하는 `catID` 매개 변수입니다.  
  
```
REQUIRED_CATEGORY( catID )
```  
  
### <a name="parameters"></a>매개 변수  
 `catID`  
 [in] A **CATID** 상수 또는 변수 필요한 범주에 대 한 전역 고유 식별자 (GUID)를 보유 합니다. 주소 `catID` 수행 되 고 지도에 추가 합니다. 스톡 범주 선택에 대 한 아래 표를 참조 하십시오.  
  
### <a name="remarks"></a>설명  
 지도에 나열 된 구성 요소 범주는 자동으로 등록 모듈을 등록 하는 클래스에 연결 된 경우 [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) 또는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로입니다.  
  
 클라이언트를 해당 형식의 인스턴스를 만들 필요 없이 해당 기능 및 요구 사항을 확인 하려면 클래스에 대해 등록 된 범주 정보를 사용할 수 있습니다. 예를 들어, 컨트롤 컨테이너에서 데이터 바인딩을 지원 해야 할 수 있습니다. 컨테이너 알아볼 수 해당 컨트롤에 필요한 범주에 대 한 범주 관리자를 쿼리하여 컨트롤을 호스트 하는 데 필요한 기능을 포함 하는 경우. 컨테이너는 필요한 기능을 지원 하지 않으면 COM 개체를 호스트할 거부할 수 있습니다.  
  
 샘플 목록에 포함 되는 구성 요소 범주에 대 한 자세한 내용은 참조 하십시오. [무엇 구성 요소 범주 이며 어떻게 작동 합니까](http://msdn.microsoft.com/library/windows/desktop/ms694322) Windows sdk에서입니다.  
  
### <a name="a-selection-of-stock-categories"></a>스톡 범주 선택  
  
|설명|기호|레지스트리 GUID|  
|-----------------|------------|-------------------|  
|스크립팅 작업에|CATID_SafeForScripting|{7DD95801-9882-11CF-9FA9-00AA006C42C4}|  
|초기화에 안전 하 게 보호|CATID_SafeForInitializing|{7DD95802-9882-11CF-9FA9-00AA006C42C4}|  
|단순 프레임 사이트 포함 항목|CATID_SimpleFrameControl|{157083E0-2368-11cf-87B9-00AA006C8166}|  
|단순 데이터 바인딩|CATID_PropertyNotifyControl|{157083E1-2368-11cf-87B9-00AA006C8166}|  
|고급 데이터 바인딩|CATID_VBDataBound|{157083E2-2368-11cf-87B9-00AA006C8166}|  
|창 없는 컨트롤|CATID_WindowlessObject|{1D06B600-3AE3-11cf-87B9-00AA006C8166}|  
|인터넷 인식 개체|참조 [인터넷 인식 개체](http://msdn.microsoft.com/library/windows/desktop/ms690561) 샘플 목록에 대 한 Windows sdk입니다.||  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#135](../../atl/codesnippet/cpp/category-macros_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)
