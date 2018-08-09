---
title: helpstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: df452614bfd5ee95a810300809678e28abfbf8ef
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643162"
---
# <a name="helpstring"></a>helpstring
적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ helpstring(  
   "string"  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *string*  
 텍스트 도움말 문자열입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **helpstring** c + + 특성에 동일한 기능을 합니다 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 하세요 [defaultvalue](../windows/defaultvalue.md) 사용 하는 방법의 예제 **helpstring**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**인터페이스**하십시오 **typedef**를 **클래스**, 메서드, 속성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [도움말 파일](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   