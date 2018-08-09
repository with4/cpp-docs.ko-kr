---
title: appobject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.appobject
dev_langs:
- C++
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78cc02c4f4d39b2bcba4c79a07ec84b9657cb66b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651199"
---
# <a name="appobject"></a>appobject
전체.exe 응용 프로그램을 사용 하 여 연결 되며 함수 및 coclass의 속성에서이 전역적으로 사용할 수 있는지 나타냅니다는 응용 프로그램 개체는 coclass를 식별 [형식 라이브러리](../mfc/automation-clients-using-type-libraries.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[appobject]  
```  
  
## <a name="remarks"></a>설명  
 합니다 **appobject** c + + 특성에 동일한 기능을 합니다 [appobject](http://msdn.microsoft.com/library/windows/desktop/aa366726) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 다음 코드를 포함 하는 특성 블록 뒤에 간단한 클래스 정의 보여 줍니다 **appobject**:  
  
```cpp  
// cpp_attr_ref_appobject.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];  
  
[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]  
__interface ICustom {};  
  
[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]  
class A : public ICustom {  
   int i;  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|`coclass`|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   