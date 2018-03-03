---
title: helpstring | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f3df545f5d87d36c26d999dc3a5fbee8720830c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="helpstring"></a>helpstring
적용 되는 요소에 설명 하는 데 사용 되는 문자열을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string`  
 도움말 문자열의 텍스트입니다.  
  
## <a name="remarks"></a>설명  
 **helpstring** c + + 특성에 동일한 기능을는 [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 [defaultvalue](../windows/defaultvalue.md) 사용 하는 방법의 예 **helpstring**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`interface``typedef`, **클래스**, 메서드, 속성|  
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
