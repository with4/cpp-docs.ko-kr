---
title: max_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.max_is
dev_langs:
- C++
helpviewer_keywords:
- max_is attribute
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2799039aa2c198bcea3784876d8299fcaec59b20
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012451"
---
# <a name="maxis"></a>max_is
유효한 배열 인덱스에 대 한 최대값을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ max_is(  
   "expression"  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *식*  
 하나 이상의 C 언어 식입니다. 빈 인수 슬롯 허용 됩니다.  
  
## <a name="remarks"></a>설명  
 합니다 **max_is** c + + 특성에 동일한 기능을 합니다 [max_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL 특성입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|필드에 **구조체** 하거나 **union**인터페이스 매개 변수, 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|**size_is**|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="example"></a>예  
 참조 [first_is](../windows/first-is.md) 배열 섹션을 지정 하는 방법의 예입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [length_is](../windows/length-is.md)   
 [size_is](../windows/size-is.md)   