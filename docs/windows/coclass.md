---
title: "coclass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.coclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "coclass attribute"
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# coclass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM 인터페이스를 구현 하는 COM 개체를 만듭니다.  
  
## 구문  
  
```  
  
[coclass]  
  
```  
  
## 설명  
 해당  **coclass** C\+\+ 특성 생성 된.idl 파일의 coclass 구문을 넣습니다.  
  
 Coclass를 정의 하는 경우 지정할 수도 있습니다 해당  [uuid](../windows/uuid-cpp-attributes.md),  [버전](../windows/version-cpp.md),  [스레딩](../windows/threading-cpp.md),  [vi\_progid](../windows/vi-progid.md), 및  [progid](../windows/progid.md) 특성.  그 중 하나를 지정 하지 않으면 생성 됩니다.  
  
 클래스와 함께 두 개의 헤더 파일을 포함 하는 경우는  **coclass** 특성 및 GUID를 지정 하지 않은 컴파일러 두 클래스 모두에 대해 동일한 GUID를 사용 합니다 및 MIDL 오류가 발생 합니다.  따라서 사용 해야 하는 `uuid` 특성을 사용 하는 경우  **coclass**.  
  
 **ATL 프로젝트**  
  
 이 특성은 클래스 또는 구조체 정의 ATL 프로젝트에 앞에 해당 합니다.  
  
-   코드 또는 개체에 대 한 자동 등록을 지원 하기 위해 데이터를 삽입 합니다.  
  
-   코드 또는 COM 클래스 팩터리 개체를 지원 하기 위해 데이터를 삽입 합니다.  
  
-   코드 또는 데이터를 구현 하려면 추가  **IUnknown** 개체가 COM에서 생성할 수 있는 개체를 확인 합니다.  
  
 특히, 다음 기본 클래스를 대상 개체에 추가 됩니다.  
  
-   [CComCoClass 클래스](../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리 및 집계 모델을 제공 합니다.  
  
-   [CComObjectRootEx 클래스](../atl/reference/ccomobjectrootex-class.md) 가 지정 된 스레딩 모델 클래스를 기반으로 서식 파일은  [스레딩](../windows/threading-cpp.md) 특성.  경우는  **스레딩** 속성이 지정 되지 않은, 아파트 모델 스레딩의 기본입니다.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) 경우 추가 되는  [를 만들 수 없도록](../windows/noncreatable.md) 특성의 대상 개체를 지정 하지.  
  
 마지막으로, 포함 된 IDL을 사용 하 여 정의 되지 않은 모든 이중 인터페이스에서 해당 대체 됩니다  [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 클래스입니다.  이중 인터페이스가 포함된 IDL에 정의 되어 있는 경우 특정 인터페이스 기본 목록에는 수정 되지 않습니다.  
  
 해당  **coclass** 특성이 수도 있습니다 다음 함수 삽입 된 코드를 통해 또는 경우에 사용할 수 있는 `GetObjectCLSID`, 기본 클래스에서 정적 메서드로 `CComCoClass`:  
  
-   `UpdateRegistry`대상 클래스는 클래스 팩터리를 등록합니다.  
  
-   `GetObjectCLSID`를 등록 하기와 관련 된도 사용 하 여 대상 클래스의 CLSID 얻을 수 있습니다.  
  
-   **GetObjectFriendlyName** 형식의 문자열을 반환 하는 기본적으로 "\<*대상 클래스 이름*을\>  `Object`".  이 함수는 이미 있는 경우에 추가 되지 않습니다.  이 함수에 친숙 한 이름을 자동으로 생성 하는 것 보다 반환할 대상 클래스를 추가 합니다.  
  
-   **GetProgID**, 등록에 관련, 함께 지정 된 문자열을 반환의  [progid](../windows/progid.md) 특성입니다.  
  
-   **GetVersionIndependentProgID** 와 동일한 기능이 있습니다  **GetProgID**를 지정 하는 문자열을 반환 하지만  [vi\_progid](../windows/vi-progid.md).  
  
 다음 변경 내용은 COM 맵에 관련 된, 대상 클래스에 수행 됩니다.  
  
-   COM 맵에 대상 클래스에서 파생 되는 모든 인터페이스에 대 한 항목 및 지정 된 모든 항목이 추가 되는  [COM 인터페이스 진입점](../mfc/com-interface-entry-points.md) 특성 또는 그에 필요한는  [집계](../windows/aggregates.md) 특성.  
  
-   [OBJECT\_ENTRY\_AUTO](../Topic/OBJECT_ENTRY_AUTO.md) 매크로 COM 맵에 삽입 됩니다.  이 매크로 유사한  [OBJECT\_ENTRY](http://msdn.microsoft.com/ko-kr/abd10ee2-54f0-4f94-9ec2-ddf8f4c8c8cd) 의 기능에 대상 클래스의 COM 맵 포함 필요 없지만.  
  
 클래스에 대 한.idl 파일을 생성 하는 coclass의 이름을 클래스와 같은 이름을 갖습니다.  예를 들어, 다음 샘플을 참조를 coclass에서는, MIDL 생성 헤더 파일을 통해 클라이언트에 대 한 클래스 ID를 액세스 하려면 clsid\_cmyclass를 사용 합니다.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 있는  **coclass** 특성:  
  
```  
// cpp_attr_ref_coclass1.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface I {  
   HRESULT func();  
};  
  
[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),   
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]  
class CMyClass : public I {};  
```  
  
 다음 샘플에 의해 삽입 된 코드를 표시 하는 함수는 기본 구현을 재정의 하는 방법을 보여 줍니다 있는  **coclass** 특성입니다.  참조 하십시오  [\/Fx](../build/reference/fx-merge-injected-code.md) 에서 삽입 된 코드를 보는 방법은.  모든 기본 클래스 또는 인터페이스에 대 한 클래스를 사용 하 여 나타납니다에서 삽입 된 코드입니다.   또한 클래스는 삽입 된 코드에 기본적으로 포함 되어를 coclass를 기본으로 클래스를 명시적으로 지정 하는 경우 특성 공급자 코드에 지정 된 형식을 사용 합니다.  
  
```  
// cpp_attr_ref_coclass2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface bb {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class CMyClass : public bb {  
public:  
   // by adding the definition of UpdateRegistry to your code,   
   // the function will not be included in the injected code  
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {  
      // you can add to the default implementation  
      CRegistryVirtualMachine rvm;  
      HRESULT hr;  
      if (FAILED(hr = rvm.AddStandardReplacements()))  
         return hr;  
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());  
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),  
         GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);  
   }  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)