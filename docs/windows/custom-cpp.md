---
title: 사용자 지정 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7222d7021665a76c7e087033f5152d2836008caa
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460934"
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
 Variant로 입력할 수 있는 값입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **사용자 지정** c + + 특성 정보를 형식 라이브러리에 배치 하면 됩니다. 형식 라이브러리에서 사용자 지정 값을 읽는 도구를 해야 합니다.  
  
 합니다 **사용자 지정** 특성이 동일한 기능을 합니다 [사용자 지정](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL 특성입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|비-COM **인터페이스**, **클래스**, **열거형**s `idl_module` 인터페이스 매개 변수, 메서드, 인터페이스 멤버 **typedef**s, **union**개이면 **구조체**s|  
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