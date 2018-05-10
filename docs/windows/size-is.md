---
title: size_is | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.size_is
dev_langs:
- C++
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7f97bb82f3387e82be5bbf120db4fed9aaa092f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="sizeis"></a>size_is
메모리의 크기에 대 한 크기의 포인터에 할당 된, 크기의 포인터 및 단일 또는 다차원 배열에 대 한 포인터 크기의 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *식*  
 크기의 포인터에 할당 된 메모리의 크기입니다.  
  
## <a name="remarks"></a>설명  
 **size_is** c + + 특성에 동일한 기능을는 [size_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL 특성입니다.  
  
## <a name="example"></a>예제  
 예를 참조 [first_is](../windows/first-is.md) 배열 섹션을 지정 하는 방법의 예입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|필드에 `struct` 또는 **union**, 매개 변수 인터페이스, 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|**max_is**|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [last_is](../windows/last-is.md)   
 [max_is](../windows/max-is.md)   
 [length_is](../windows/length-is.md)   
