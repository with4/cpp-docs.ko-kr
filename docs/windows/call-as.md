---
title: call_as | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68707ea7e00665d12165c7838b1a2ad3440f944d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860868"
---
# <a name="callas"></a>call_as
수 있도록는 [로컬](../windows/local-cpp.md) 함수를 로컬 함수를 호출 하는 원격 함수를 호출할 때 되도록 원격 함수에 매핑할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *function*  
 원격 함수 호출 될 때 호출 될 원하는 로컬 함수입니다.  
  
## <a name="remarks"></a>설명  
 **call_as** c + + 특성에 동일한 기능을는 [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL 특성입니다.  
  
## <a name="example"></a>예제  
 다음 코드는 사용 하는 방법을 보여 줍니다. **call_as** 원격 가능 하지 함수에 매핑할 (**f1**) 원격 능력이 함수 (**Remf1**):  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
