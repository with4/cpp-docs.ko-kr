---
title: coclass | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.coclass
dev_langs:
- C++
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5eb9c7e632151c039b76a0f389cd18c68c0740ab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33867014"
---
# <a name="coclass"></a>coclass
COM 인터페이스를 구현할 수 있는 COM 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[coclass]  
  
```  
  
## <a name="remarks"></a>설명  
 **coclass** c + + 특성 생성된 된.idl 파일에는 coclass 구문을 배치 합니다.  
  
 Coclass를 정의할 때 지정할 수도 있습니다는 [uuid](../windows/uuid-cpp-attributes.md), [버전](../windows/version-cpp.md), [스레딩](../windows/threading-cpp.md), [vi_progid](../windows/vi-progid.md), 및 [progid ](../windows/progid.md) 특성입니다. 중 하나라도 지정 되지 않은 경우 생성 됩니다.  
  
 두 개의 헤더 파일 사용 하 여 클래스를 포함 하는 경우는 **coclass** 특성 및 GUID를 지정 하지 않으면 컴파일러에서 두 클래스 모두에 대해 동일한 GUID를 사용 하 고 MIDL 오류가 발생 하 합니다.  따라서 사용 해야는 `uuid` 사용 하는 경우 특성 **coclass**합니다.  
  
 **ATL 프로젝트**  
  
 이 특성은 클래스 또는 구조체 정의 ATL 프로젝트에서 앞에 표시 하는 경우 해당:  
  
-   코드 또는 개체에 대 한 자동 등록을 지원 하기 위해 데이터를 삽입 합니다.  
  
-   코드 또는 개체에 대 한 COM 클래스 팩터리를 지원 하기 위해 데이터를 삽입 합니다.  
  
-   코드 또는 구현 하는 데이터를 삽입 합니다. **IUnknown** COM 생성 가능 개체는 개체를 확인 합니다.  
  
 특히 다음과 같은 기본 클래스는 대상 개체에 추가 됩니다.  
  
-   [CComCoClass 클래스](../atl/reference/ccomcoclass-class.md) 개체에 대 한 기본 클래스 팩터리와 집계 모델을 제공 합니다.  
  
-   [CComObjectRootEx 클래스](../atl/reference/ccomobjectrootex-class.md) 에서 지정한 스레딩 모델 클래스를 기반으로 템플릿을는 [스레딩](../windows/threading-cpp.md) 특성입니다. 경우는 **스레딩** 특성이 지정 되지 않은, 스레딩 모델 기본값인 아파트 합니다.  
  
-   [IProvideClassInfo2Impl](../atl/reference/iprovideclassinfo2impl-class.md) 경우 추가 되는 [noncreatable](../windows/noncreatable.md) 대상 개체에 대 한 특성을 지정 하지 않으면 합니다.  
  
 마지막으로, 포함된 IDL를 사용 하 여 정의 되지 않은 모든 이중 인터페이스 아래 템플릿으로 바뀝니다 해당 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 클래스입니다. 이중 인터페이스 포함된 IDL에 정의 된 경우에 기본 목록에서는 특정 인터페이스 수정 되지 않습니다.  
  
 **coclass** 특성 사용 하면 다음 함수는 대/소문자 또는 삽입 된 코드를 통해 사용할 수 있는 `GetObjectCLSID`, 기본 클래스의 정적 메서드로 `CComCoClass`:  
  
-   `UpdateRegistry` 대상 클래스의 클래스 팩터리를 등록합니다.  
  
-   `GetObjectCLSID`를 등록에 관련 된 사용할 수도 있습니다는 대상 클래스의 CLSID를 얻으려고 합니다.  
  
-   **GetObjectFriendlyName** 기본적으로 형식 문자열을 반환 "\<*대상 클래스 이름*> `Object`"입니다. 이 함수가 이미 있으면 추가 되지 않습니다. 이 함수를 자동으로 생성 된 것 친숙 한 이름을 반환 하는 대상 클래스를 추가 합니다.  
  
-   **GetProgID**등록에 관련 된,와 지정 된 문자열을 반환 된 [progid](../windows/progid.md) 특성입니다.  
  
-   **GetVersionIndependentProgID** 동일한 기능이 **GetProgID**, 지정 된 문자열을 반환 하지만 [vi_progid](../windows/vi-progid.md)합니다.  
  
 대상 클래스를 COM 맵 관련이 있는 다음과 같은 변경 내용은 적용 됩니다.  
  
-   Com 대상 클래스에서 파생 되는 모든 인터페이스에 대 한 항목 및로 지정 된 항목을 모두 사용 하 여 추가 되는 [COM 인터페이스 진입점](../mfc/com-interface-entry-points.md) 특성 또는에 필요한는 [집계](../windows/aggregates.md) 특성입니다.  
  
-   [OBJECT_ENTRY_AUTO](../atl/reference/object-map-macros.md#object_entry_auto) COM 맵으로 매크로가 삽입 됩니다.
  
 클래스에 대 한.idl 파일에서 생성 된 coclass의 이름에는 클래스와 동일한 이름을 갖습니다.  예를 들어 다음 샘플에서는 참조 클래스 ID coclass CMyClass, MIDL에서 생성 된 헤더 파일을 통해 클라이언트에 대 한 액세스를 CLSID_CMyClass를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 사용 하 여 **coclass** 특성:  
  
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
  
 다음 샘플에서는 의해 삽입 된 코드에 표시 되는 함수의 기본 구현을 재정의 하는 방법을 보여 줍니다.는 **coclass** 특성입니다. 삽입된 코드 보기에 대한 자세한 정보는 [/Fx](../build/reference/fx-merge-injected-code.md) 를 참조하세요. 모든 기본 클래스 또는 인터페이스 클래스에 대해 사용 하는 삽입된 된 코드에 나타납니다.   또한 삽입된 된 코드에서 기본적으로는 클래스가 포함 되 고 명시적으로 해당 클래스를 기본 프로그램 coclass에 대 한를 지정 하는 경우 특성 공급자 코드에 지정 된 폼을 사용 합니다.  
  
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
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [COM 특성](../windows/com-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [appobject](../windows/appobject.md)