---
title: "개체 맵 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
dev_langs: C++
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 626744eb9f2d9dbe6a013bd329406150af35ecca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="object-map-macros"></a>개체 맵 매크로
이러한 매크로 개체 지도 및 항목을 정의 합니다.  
  
|||  
|-|-|  
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|개체 맵의에 입력 됩니다 있는 클래스 개체의 텍스트 설명을 지정할 수 있습니다.|  
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|개체 맵의에 ATL 개체를 입력 하 고 레지스트리를 업데이트 합니다. 개체의 인스턴스를 만듭니다.|  
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="declare_object_description"></a>DECLARE_OBJECT_DESCRIPTION  
 클래스 개체에 대 한 텍스트 설명을 지정할 수 있습니다.  
  
```
DECLARE_OBJECT_DESCRIPTION( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 클래스 개체의 설명입니다.  
  
### <a name="remarks"></a>설명  
 ATL이이 설명을 통해 개체 맵의 시작는 [OBJECT_ENTRY](http://msdn.microsoft.com/en-us/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) 매크로입니다.  
  
 `DECLARE_OBJECT_DESCRIPTION`구현 하는 `GetObjectDescription` 재정의 하는 데 사용할 수 있는 함수는 [CComCoClass::GetObjectDescription](ccomcoclass-class.md#getobjectdescription) 메서드.  

  
 `GetObjectDescription` 함수 호출한 **IComponentRegistrar::GetComponents**합니다. **IComponentRegistrar** 등록 하 고 개별 구성 요소 DLL의 등록을 취소할 수 있는 자동화 인터페이스입니다. ATL 프로젝트 마법사를 구성 요소 등록자 개체를 만들 경우 마법사는 자동으로 구현 된 **IComponentRegistrar** 인터페이스입니다. **IComponentRegistrar** Microsoft Transaction Server에서 주로 사용 됩니다.  
  
 ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]  
  
##  <a name="object_entry_auto"></a>OBJECT_ENTRY_AUTO  
 개체 맵의에 ATL 개체를 입력 하 고 레지스트리를 업데이트 합니다. 개체의 인스턴스를 만듭니다.  
  
```
OBJECT_ENTRY_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] `class`라는 C++ 클래스에 의해 구현되는 COM 클래스의 CLSID입니다.  
  
 `class`  
 [in] `clsid`로 표현되는 COM 클래스를 구현하는 C++ 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.  
  
 `OBJECT_ENTRY_AUTO`생성자 클래스 및 클래스 팩터리 생성자 클래스의 함수 포인터 입력 `CreateInstance` ATL 개체 자동 생성 된 지도에이 개체에 대 한 함수입니다. 때 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver) 는 개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트를 호출 합니다.  

  
 다음 표에서이 매크로에 두 번째 매개 변수로 제공 하는 클래스에서 가져온 개체 지도에 추가 정보가 방법을 설명 합니다.  
  
|에 대 한 정보|가져온|  
|---------------------|-------------------|  
|COM 등록|[레지스트리 매크로](../../atl/reference/registry-macros.md)|  
|클래스 팩터리 만들기|[클래스 팩터리 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|인스턴스 만들기|[집계 매크로](../../atl/reference/aggregation-and-class-factory-macros.md)|  
|구성 요소 범주 등록|[범주 매크로](../../atl/reference/category-macros.md)|  
|클래스 수준 초기화 및 정리|[ObjectMain](ccomobjectrootex-class.md#objectmain)|  

  
##  <a name="object_entry_non_createable_ex_auto"></a>OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO  
 개체를 등록하고 초기화해야 하지만 `CoCreateInstance`를 통해 외부적으로 생성할 수 없도록 지정할 수 있습니다.  
  
```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] `class`라는 C++ 클래스에 의해 구현되는 COM 클래스의 CLSID입니다.  
  
 `class`  
 [in] `clsid`로 표현되는 COM 클래스를 구현하는 C++ 클래스의 이름입니다.  
  
### <a name="remarks"></a>설명  
 개체 항목 매크로는 클래스 등록, 초기화 및 만들기를 지원하도록 프로젝트의 전역 범위에 배치됩니다.  
  
 `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO`개체를 등록 하 고 초기화를 지정할 수 있습니다 (참조 [OBJECT_ENTRY_AUTO](#object_entry_auto) 자세한 내용은)를 통해 생성할 수 없도록 하지만 `CoCreateInstance`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)
