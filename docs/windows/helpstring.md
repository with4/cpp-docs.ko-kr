---
title: "helpstring | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstring attribute [C++]"
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자열이 적용되는 요소를 설명하는 데 사용되는 문자열을 지정합니다.  
  
## 구문  
  
```  
  
      [ helpstring(  
   "string"  
) ]  
```  
  
#### 매개 변수  
 `string`  
 도움말 문자열의 텍스트입니다.  
  
## 설명  
 **Helpstring** C\+\+ 특성을 동일한 기능을가지고 있는  [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [defaultvalue](../windows/defaultvalue.md) 예를 사용 하는 방법에 대 한  **helpstring**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface` `typedef`,  **클래스**, 메서드, 속성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpfile](../windows/helpfile.md)   
 [helpcontext](../windows/helpcontext.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)