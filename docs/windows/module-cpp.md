---
title: "모듈 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.module
dev_langs: C++
helpviewer_keywords: module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75b41ea146096a60210918b5f21e7b6278e35001
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="module-c"></a>module(C++)
.Idl 파일의 라이브러리 블록을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ module (  
   type=dll,  
   name=string,  
   version=1.0,  
   uuid=uuid,  
   lcid=integer,  
   control=boolean,  
   helpstring=string,  
   helpstringdll=string,  
   helpfile=string,  
   helpcontext=integer,  
   helpstringcontext=integer,  
   hidden=boolean,  
   restricted=boolean,  
   custom=string,  
   resource_name=string,  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 ***type***  (선택 사항)  
 다음 중 하나일 수 있습니다.  
  
-   **dll** 결과 DLL이 In-process COM 서버로 작동하도록 허용하는 함수 및 클래스를 추가합니다. 기본값입니다.  
  
-   **exe** 결과 실행 파일이 Out-of-process COM 서버로 작동하도록 허용하는 함수 및 클래스를 추가합니다.  
  
-   **service** 결과 실행 파일이 NT 서비스로 작동하도록 허용하는 함수 및 클래스를 추가합니다.  
  
-   **unspecified** 모듈 특성과 관련된 ATL 코드의 삽입, ATL 모듈 클래스, 전역 인스턴스 _AtlModule 및 진입점 함수의 삽입을 사용하지 않도록 설정합니다.  프로젝트의 기타 특성으로 인한 ATL 코드의 삽입은 허용합니다.  
  
 ***name***  (선택 사항)  
 라이브러리 블록의 이름입니다.  
  
 ***version***  (선택 사항)  
 라이브러리 블록에 할당하려는 버전 번호입니다. 기본값은 1.0입니다.  
  
 `uuid`  
 라이브러리에 대한 고유 ID입니다. 이 매개 변수를 생략하면 라이브러리에 대한 ID가 자동으로 생성됩니다. 라이브러리 블록의 *uuid* 를 검색해야 할 수 있습니다. **__uuidof(***libraryname***)**식별자를 사용하여 수행할 수 있습니다.  
  
 **lcid**  
 지역화 매개 변수입니다. 자세한 내용은 [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) 를 참조하세요.  
  
 **control** (선택 사항)  
 라이브러리의 모든 coclass가 컨트롤임을 지정합니다.  
  
 **helpstring**  
 형식 라이브러리를 지정합니다.  
  
 ***helpstringdll***  (선택 사항)  
 문서 문자열 조회를 수행하는 데 사용할 .dll 파일의 이름을 설정합니다. 자세한 내용은 [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) 을 참조하세요.  
  
 **helpfile** (선택 사항)  
 형식 라이브러리에 대한 도움말 파일의 이름입니다.  
  
 **helpcontext** (선택 사항)  
 이 형식 라이브러리에 대한 도움말 ID입니다.  
  
 **helpstringcontext** (선택 사항)  
 자세한 내용은 [helpstringcontext](../windows/helpstringcontext.md) 를 참조하세요.  
  
 **hidden** (선택 사항)  
 전체 라이브러리가 표시되지 않도록 합니다. 이 사용법은 컨트롤과 함께 사용하기 위한 것입니다. 호스트는 확장된 속성을 사용하여 컨트롤을 래핑하는 새로운 형식 라이브러리를 만들어야 합니다. 자세한 내용은 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL 특성을 참조하세요.  
  
 **restricted** (선택 사항)  
 라이브러리의 멤버를 임의로 호출할 수 없습니다. 자세한 내용은 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL 특성을 참조하세요.  
  
 ***custom***  (선택 사항)  
 하나 이상의 특성입니다. [custom](../windows/custom-cpp.md) 특성과 비슷합니다. `custom` 에 대한 첫 번째 매개 변수는 특성이 GUID입니다. 예:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
 **resource_name**  
 DLL, 실행 파일 또는 서비스의 APP ID를 등록하는 데 사용되는 .rgs 파일의 문자열 리소스 ID입니다. 모듈이 형식 서비스인 경우 서비스 이름을 포함하는 문자열의 ID를 가져오는 데에도 이 인수가 사용됩니다.  
  
> [!NOTE]
>  서비스 이름을 포함하는 문자열과 .rgs 파일 모두 동일한 숫자 값을 포함해야 합니다.  
  
## <a name="remarks"></a>설명  
 **restricted** 매개 변수를 [emitidl](../windows/emitidl.md)로 지정하지 않는 경우, C++ 특성을 사용하는 프로그램에 **module** 이 필요합니다.  
  
 소스 코드가 **module** 특성 외에 [dispinterface](../windows/dispinterface.md), [dual](../windows/dual.md), [object](../windows/object-cpp.md)특성 또는 [coclass](../windows/coclass.md)를 암시하는 특성을 사용하는 경우 라이브러리 블록이 만들어집니다.  
  
 .idl 파일 하나에 라이브러리 블록 하나가 허용됩니다. 소스 코드에 여러 모듈 항목이 병합되며, 가장 최근의 매개 변수 값이 구현됩니다.  
  
 ATL을 사용하는 프로젝트 내에서 이 특성을 사용하는 경우 특성의 동작이 변경됩니다. 위 동작 외에도 특성은 올바른 형식 및 추가 지원 코드의 전역 개체( **_AtlModule**이라고 함)를 삽입합니다. 독립 실행형 특성의 경우 올바른 모듈 형식에서 파생된 클래스를 삽입합니다. 클래스에 적용되는 특성의 경우 올바른 모듈 형식의 기본 클래스를 추가합니다. 올바른 형식은 `type` 매개 변수의 값에 의해 결정됩니다.  
  
-   `type` = **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) 는 COM 서버에 필요한 기본 클래스 및 표준 DLL 진입점으로 사용됩니다. 이러한 진입점은 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583), [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162), [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457), [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368)및 [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891)입니다.  
  
-   `type` = **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) 는 기본 클래스 및 표준 실행 파일 진입점 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)으로 사용됩니다.  
  
-   `type` = **service**  
  
     [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) 는 기본 클래스 및 표준 실행 파일 진입점 [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)으로 사용됩니다.  
  
-   `type` = **unspecified**  
  
     모듈 특성과 관련된 ATL 코드의 삽입이 사용되지 않습니다.  
  
## <a name="example"></a>예  
 다음 코드는 생성된 .idl 파일의 라이브러리 블록을 만드는 방법을 보여 줍니다.  
  
```  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 다음 코드는 **module**사용 결과 삽입된 코드에 나타날 수 있는 함수의 자체 구현을 제공할 수 있음을 보여 줍니다. 삽입된 코드 보기에 대한 자세한 정보는 [/Fx](../build/reference/fx-merge-injected-code.md) 를 참조하세요. **module** 특성에 의해 삽입된 함수 중 하나를 재정의하려면 함수의 구현을 포함할 클래스를 만들고 여기에 **module** 특성을 적용합니다.  
  
```  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [라이브러리](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [도움말 파일](../windows/helpfile.md)   
 [version](../windows/version-cpp.md)   
