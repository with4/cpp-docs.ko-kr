---
title: odl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.odl
dev_langs: C++
helpviewer_keywords: odl attribute
ms.assetid: 75dcb314-b50f-4a63-9180-507ac1bc78f3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb7525fb57a336defd6d2d50dae4bc0ee988c1ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="odl"></a>odl
개체 설명 언어 ODL () 인터페이스는 인터페이스를 식별합니다. MIDL 컴파일러 필요 하지 않습니다는 **odl** 특성; 이전.odl 파일의 호환에만 인식 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[odl]  
  
```  
  
## <a name="remarks"></a>설명  
 **odl** c + + 특성에 동일한 기능을는 [odl](http://msdn.microsoft.com/library/windows/desktop/aa367126) MIDL 특성입니다.  
  
## <a name="example"></a>예  
  
```  
// cpp_attr_ref_odl.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLIb")];  
  
[odl, oleautomation, dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyInterface  
{  
   HRESULT x();  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
class cmyClass : public IMyInterface  
{  
public:  
   HRESULT x(){}  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
