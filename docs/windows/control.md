---
title: "컨트롤 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.control
dev_langs:
- C++
helpviewer_keywords:
- Control attribute
ms.assetid: 3d046bb2-4afe-4cb8-a762-233b296e1975
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00e9ce0a3e310ad9d07f41b0053ed5249a35a339
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="control"></a>컨트롤
사용자 정의 형식 컨트롤 임을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[control]  
  
```  
  
## <a name="remarks"></a>설명  
 **제어** 내재 하 고는 [coclass](../windows/coclass.md) 특성입니다. **제어** c + + 특성에 동일한 기능을는 [제어](http://msdn.microsoft.com/library/windows/desktop/aa366764) MIDL 특성입니다.  
  
## <a name="example"></a>예  
  
```  
// cpp_attr_ref_control.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="Test", control=true)];  
  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[coclass, control, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
class CTest : public ICustom {};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
