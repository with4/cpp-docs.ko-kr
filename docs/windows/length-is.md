---
title: length_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.length_is
dev_langs:
- C++
helpviewer_keywords:
- length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d30a467bd929c68c35e06861087ec7f47d1f2d51
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011909"
---
# <a name="lengthis"></a>length_is
전송할 배열 요소의 수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ length_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *식*  
 하나 이상의 C 언어 식입니다. 빈 인수 슬롯 허용 됩니다.  
  
## <a name="remarks"></a>설명  
 합니다 **length_is** c + + 특성에 동일한 기능을 합니다 [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 참조 [first_is](../windows/first-is.md) 배열 섹션을 지정 하는 방법의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|필드에 **구조체** 하거나 **union**인터페이스 매개 변수, 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   