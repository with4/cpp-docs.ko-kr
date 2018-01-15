---
title: "(옵션) (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.optional
dev_langs: C++
helpviewer_keywords: optional attribute
ms.assetid: 86656a66-8e11-4589-8e30-9b0f34eeed03
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 028cb0f911ac389e4ad17f54fc16e24f29c8d9db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="optional-c"></a>optional(C++)
멤버 함수에 대 한 선택적 매개 변수를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[optional]  
  
```  
  
## <a name="remarks"></a>설명  
 **선택적** c + + 특성에 동일한 기능을는 [선택적](http://msdn.microsoft.com/library/windows/desktop/aa367132) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 다음 코드 방법을 **선택적** 사용 될 수 있습니다.  
  
```  
// cpp_attr_ref_optional.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl : IDispatch  
{  
   [id(1)] long procedure ([in, optional] VARIANT i);  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
