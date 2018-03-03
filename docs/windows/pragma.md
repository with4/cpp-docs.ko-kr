---
title: pragma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36016ae4af32ead520c8d9919840d267e9d46211
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pragma"></a>pragma
인용 부호를 사용 하지 않고 생성 된.idl 파일에 지정 된 문자열을 내보냅니다. 이어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *pragma_statement*  
 생성 된.idl 파일로 이동 하려는 pragma입니다.  
  
## <a name="remarks"></a>설명  
 **pragma** c + + 특성에 동일한 기능을는 [pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL 특성입니다.  
  
## <a name="example"></a>예  
  
```  
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
