---
title: support_error_info | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e07d218158ff5615fbdc26a5f48b7cf828596ed
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014171"
---
# <a name="supporterrorinfo"></a>support_error_info
자세한 오류 반환에 대한 지원을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ support_error_info(  
   error_interface=uuid  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *error_interface*  
 구현 하는 인터페이스의 식별자 `IErrorInfo`합니다.  
  
## <a name="remarks"></a>설명  
 **support_error_info** C++ 특성은 대상 개체에서 발생한 자세한 상황별 오류를 클라이언트에 반환하는 작업에 대한 지원을 구현합니다. 오류를의 메서드를 지원 하려면 개체에 대 한는 `IErrorInfo` 개체에서 인터페이스를 구현 해야 합니다. 자세한 내용은 [IDispatch 및 IErrorInfo 지원](../atl/supporting-idispatch-and-ierrorinfo.md)을 참조하세요.  
  
 이 특성은 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 클래스를 대상 개체에 기본 클래스로 추가합니다. 기본 구현에서는이 인해 `ISupportErrorInfo` 단일 인터페이스가 개체에서 오류를 생성 하는 경우에 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 코드에 대 한 기본 지원을 추가 합니다 `ISupportErrorInfo` 인터페이스는 `CMyClass` 개체입니다.  
  
```cpp  
// cpp_attr_ref_support_error_info.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="mymod")];  
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]  
__interface IMyErrors  
{  
};  
  
[ coclass, support_error_info("IMyErrors"),  
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]  
class CMyClass  
{  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**|  
|**반복 가능**|예|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   