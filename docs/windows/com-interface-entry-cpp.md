---
title: "com_interface_entry (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.com_interface_entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com_interface_entry attribute"
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# com_interface_entry (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대상 클래스의 COM 맵 인터페이스 항목을 추가합니다.  
  
## 구문  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### 매개 변수  
 *com\_interface\_entry*  
 항목의 실제 텍스트를 포함 하는 문자열입니다.  사용 가능한 값 목록을 보려면을 참조 하십시오.  [COM\_INTERFACE\_ENTRY 매크로](../Topic/COM_INTERFACE_ENTRY%20Macros.md).  
  
## 설명  
 `com_interface_entry` C \+ \+ 특성에 있는 대상 개체의 COM 인터페이스 맵이 통화할된 문자열의 내용을 삽입 합니다.  특성 대상 개체에 한 번 적용 되는 경우 기존 인터페이스 맵 부분에 항목이 삽입 됩니다.  특성 반복적으로 같은 대상 개체에 적용 되는 경우 항목이 인터페이스 맵 수신 된 순서 대로 시작 부분에 삽입 됩니다.  
  
 필요로 하는이 특성에  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 특성 \(또는이 중 하나를 의미 하는 다른 특성\)도 적용 될 같은 요소를 합니다.  다른 두 가지는 단일 특성을 사용 하는 경우에 자동으로 적용 됩니다.  예를 들어, 경우  **progid** 적용 된  **vi\_progid** 및  **coclass** 적용 됩니다.  
  
 때문에 가장 먼저 사용 하는 `com_interface_entry` 인터페이스 맵 시작 부분에 삽입 되는 새 인터페이스 COM\_INTERFACE\_ENTRY 다음 형식 중 하나 여야 합니다.  
  
-   COM\_INTERFACE\_ENTRY  
  
-   COM\_INTERFACE\_ENTRY\_IID  
  
-   COM\_INTERFACE\_ENTRY2  
  
-   COM\_INTERFACE\_ENTRY2\_IID  
  
 자세한 사용법은 `com_interface_entry` 특성 지원 되는 모든 COM\_INTERFACE\_ENTRY 형식을 사용할 수 있습니다.  
  
 ATL 인터페이스 맵에서 첫 번째 항목을 id로 사용 하기 때문에이 제한이 필요는  **IUnknown**. 따라서 사용할 인터페이스를 입력 해야 합니다.  실제 COM 인터페이스 인터페이스 구조에서 첫 번째 항목을 지정 하지 않기 때문 예를 들어, 다음 코드 샘플에서는 올바르지 않습니다.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## 예제  
 두 항목의 기존 COM 인터페이스 맵이 다음 코드를 추가  **CMyBaseClass**.  첫 번째는 표준 인터페이스 이며 숨깁니다. 두 번째는  **IDebugTest** 인터페이스입니다.  
  
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
  
 결과 COM 개체 구조에 대 한  **CMyBaseClass** 는 다음과 같습니다.  
  
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
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|예|  
|**필수 특성**|하나 이상의 다음:  **coclass**,  **progid**, 또는  **vi\_progid**.|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)