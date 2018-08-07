---
title: noncreatable | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4055d541fa60c714262a64466734bc2b2323775b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877825"
---
# <a name="noncreatable"></a>noncreatable
단독으로 인스턴스화할 수 없는 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[noncreatable]  
  
```  
  
## <a name="remarks"></a>설명  
 **noncreatable** c + + 특성에 동일한 기능을는 [noncreatable](http://msdn.microsoft.com/library/windows/desktop/aa367118) MIDL 특성을 생성 된 자동으로 전달 됩니다. 컴파일러에서 IDL 파일입니다.  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작이 변경 됩니다. 위의 동작 외에도 특성도 삽입 합니다.는 [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) 매크로입니다. Atl 나타냅니다이 매크로 개체 외부에서 만들 수 없습니다.  
  
## <a name="example"></a>예제  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
