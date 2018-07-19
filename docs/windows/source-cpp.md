---
title: 원본 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.source
dev_langs:
- C++
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11ee58fb2d500a7194fb08ee18b1af5cc7897830
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889864"
---
# <a name="source-c"></a>source(C++)
클래스를 연결 지점에 대 한 COM 개체의 소스 인터페이스를 지정합니다. 속성 또는 메서드 멤버 개체 또는 이벤트의 원본인 VARIANT를 반환 하는지 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ source(  
   interfaces  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `interfaces`  
 하나 이상의 인터페이스를 지정 하는 소스를 적용 하는 경우는 특성 클래스입니다. 이 매개 변수는 소스 메서드나 속성에 적용 되는 사용 되지 않습니다.  
  
## <a name="remarks"></a>설명  
 **소스** c + + 특성에 동일한 기능을는 [소스](http://msdn.microsoft.com/library/windows/desktop/aa367166) MIDL 특성입니다.  
  
 사용할 수는 [기본](../windows/default-cpp.md) 을 개체에 대 한 기본 소스 인터페이스를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// cpp_attr_ref_source.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]  
   HRESULT get_I([out, retval]long *i);  
};  
  
[object, uuid(11111111-1111-1111-1111-111111111131)]  
__interface c  
{  
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]   
   HRESULT et_I([out, retval]long *i);  
};  
  
[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]  
class N : public b  
{  
};  
  
[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]  
class NN : public b  
{  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, `interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass** (클래스 또는 구조체에 적용 됨) 하는 경우|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [coclass](../windows/coclass.md)   
