---
title: 범위 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.range
dev_langs:
- C++
helpviewer_keywords:
- range attribute
ms.assetid: f352f79e-ecb3-4cdd-9cdd-8406ef473594
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac5f0e81a7d29d89e32735224afed67f3d9c9101
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877932"
---
# <a name="range-c"></a>range(C++)
형식 정의 나 런타임에 해당 값이 설정 되는 필드에 대 한 허용 가능한 값의 범위를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ range(  
   low,   
   high  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *low*  
 하위 범위의 값입니다.  
  
 *high*  
 범위 상한 값입니다.  
  
## <a name="remarks"></a>설명  
 **범위** c + + 특성에 동일한 기능을는 [범위](http://msdn.microsoft.com/library/windows/desktop/aa367151) MIDL 특성입니다.  
  
## <a name="example"></a>예제  
  
```  
// cpp_attr_ref_range.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   HRESULT length_is1([in, range(0, 999)] long f, [in, length_is(f)] char array[10]);  
   HRESULT length_is2([in, range(-99, -1)] long f, [in, length_is("f"), size_is(10)] char *array);  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드를 인터페이스 매개 변수|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [데이터 멤버 특성](../windows/data-member-attributes.md)   
