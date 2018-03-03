---
title: com_interface_entry (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 58c74602c4170cbe0816dcdf14e0196cca44af42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cominterfaceentry-c"></a>com_interface_entry(C++)
대상 클래스의 COM 맵에 인터페이스 항목을 추가합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *com_interface_entry*  
 항목의 실제 텍스트를 포함 하는 문자열입니다. 가능한 값 목록은 참조 [COM_INTERFACE_ENTRY 매크로](../atl/reference/com-interface-entry-macros.md)합니다.  
  
## <a name="remarks"></a>설명  
 `com_interface_entry` c + + 특성 COM 인터페이스 맵을 대상 개체의 문자열의 통화할된 내용을 삽입 합니다. 특성이 두 번 대상 개체에 적용 하는 경우 항목의 기존 인터페이스 맵 시작 부분에 삽입 됩니다. 특성을 적용 하면 반복 해 서 동일한 대상 개체에 있는 항목 인터페이스 맵 수신 된 순서에서 맨 앞에 삽입 됩니다.  
  
 이 특성을 사용하려면 [coclass](../windows/coclass.md), [progid](../windows/progid.md)또는 [vi_progid](../windows/vi-progid.md) 특성(또는 이 중 하나를 암시하는 다른 특성)을 동일한 요소에 적용해야 합니다. 단일 특성을 사용하는 경우 다른 두 특성도 자동으로 적용됩니다. 예를 들어 **progid** 를 적용하면 **vi_progid** 및 **coclass** 도 적용됩니다.  
  
 때문에의 첫 번째 사용 `com_interface_entry` 인터페이스 맵 맨 앞에 삽입 될 새 인터페이스 다음 COM_INTERFACE_ENTRY 유형 중 하나 여야 합니다.  
  
-   COM_INTERFACE_ENTRY  
  
-   COM_INTERFACE_ENTRY_IID  
  
-   COM_INTERFACE_ENTRY2  
  
-   COM_INTERFACE_ENTRY2_IID  
  
 다른 용도 `com_interface_entry` 특성에는 지원 되는 모든 COM_INTERFACE_ENTRY 형식을 사용할 수 있습니다.  
  
 이 제한은 ATL 인터페이스 맵에 첫 번째 항목은 id로 사용 하기 때문에 필요한 **IUnknown**이므로, 유효한 인터페이스를 입력 해야 합니다. 예를 들어 다음 코드 샘플 올바르지 인터페이스 맵에 첫 번째 항목은 실제 COM 인터페이스를 지정 하지 않으므로 합니다.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## <a name="example"></a>예  
 다음 코드는 두 항목의 기존 COM 인터페이스 지도에 추가 **CMyBaseClass**합니다. 첫 번째는 표준 인터페이스가 고 두 번째 숨기는 **IDebugTest** 인터페이스입니다.  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 에 대 한 결과 COM 개체 맵 **CMyBaseClass** 는 다음과 같습니다.  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|예|  
|**필수 특성**|다음 중 하나 이상: **coclass**, **progid**또는 **vi_progid**.|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
