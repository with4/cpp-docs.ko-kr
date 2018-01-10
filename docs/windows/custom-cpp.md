---
title: "사용자 지정 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.custom
dev_langs: C++
helpviewer_keywords: custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55fd4ad47470a86a0a3d61cc847c20fb21768e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="custom-c"></a>custom(C++)
형식 라이브러리의 개체에 대 한 메타 데이터를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *uuid*  
 고유한 ID입니다.  
  
 *값*  
 Variant로 들어갈 수 있는 값입니다.  
  
## <a name="remarks"></a>설명  
 **사용자 지정** c + + 특성 정보를 형식 라이브러리에 배치할 수 발생 합니다. 형식 라이브러리에서 사용자 지정 값을 읽을 수 있는 도구에 필요 합니다.  
  
 **사용자 지정** 특성와 동일한 기능에는 [사용자 지정](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL 특성입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|COM이 아닌 `interface`, **클래스**, `enum`s, `idl_module` 메서드, 인터페이스 멤버, 인터페이스 매개 변수 `typedef`s **union**s, `struct`s|  
|**반복 가능**|예|  
|**필수 특성**|**coclass** (클래스에 사용) 하는 경우|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
