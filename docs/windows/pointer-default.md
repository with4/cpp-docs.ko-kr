---
title: pointer_default | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee904f9243cf642d3a942d4bc323f5ec381b0480
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877464"
---
# <a name="pointerdefault"></a>pointer_default
매개 변수 목록에 표시 되는 최상위 포인터를 제외 하 고 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *값*  
 포인터 형식에 설명 하는 값: **ptr**, `ref`, 또는 **고유**합니다.  
  
## <a name="remarks"></a>설명  
 **pointer_default** c + + 특성에 동일한 기능을는 [pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL 특성입니다.  
  
## <a name="example"></a>예제  
 예를 참조 [defaultvalue](../windows/defaultvalue.md) 의 샘플 사용에 대 한 **pointer_default**합니다.  
  
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
