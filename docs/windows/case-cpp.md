---
title: 대/소문자 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.case
dev_langs:
- C++
helpviewer_keywords:
- case attribute
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 30d665861688054a4f6b7491f449014afe646c71
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="case-c"></a>case(C++)
함께 사용 된 [switch_type](../windows/switch-type.md) 특성에 **union**합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *값*  
 처리를 제공 하려는 하는 가능한 입력된 값입니다. 유형의 **값** 다음 유형 중 하나일 수 있습니다.  
  
-   `int`  
  
-   `char`  
  
-   `boolean`  
  
-   `enum`  
  
 또는 이러한 형식의 식별자입니다.  
  
## <a name="remarks"></a>설명  
 **대/소문자** c + + 특성에 동일한 기능을는 **대/소문자** MIDL 특성입니다. 이 특성에만 사용 됩니다는 [switch_type](../windows/switch-type.md) 특성입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 사용 하 여 **대/소문자** 특성:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|멤버는 **클래스** 또는 `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
