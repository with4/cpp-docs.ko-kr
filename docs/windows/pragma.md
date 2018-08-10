---
title: pragma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9c9d347b319afc3ee84818e74029a98b1aa5484
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014301"
---
# <a name="pragma"></a>pragma
따옴표를 사용 하지 않고 생성 된.idl 파일에 지정된 된 문자열을 내보냅니다. 
  
## <a name="syntax"></a>구문  
  
```cpp  
[ pragma(  
   pragma_statement  
) ];  
```  
  
### <a name="parameters"></a>매개 변수  
 *pragma_statement*  
 생성 된.idl 파일로 이동 하려는 pragma입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **pragma** c + + 특성에 동일한 기능을 합니다 [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL 특성입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
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
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   