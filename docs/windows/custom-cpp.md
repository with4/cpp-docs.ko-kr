---
title: "custom (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.custom"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "custom attributes, defining"
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# custom (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체에 대 한 메타 데이터는 형식 라이브러리에 정의합니다.  
  
## 구문  
  
```  
  
      [ custom(  
   uuid,   
   value  
) ];  
```  
  
#### 매개 변수  
 *uuid*  
 고유한 ID입니다.  
  
 *value*  
 Variant에 넣을 수 있는 값입니다.  
  
## 설명  
 해당  **사용자 지정** C\+\+ 특성 정보에 형식 라이브러리를 생성 합니다.  형식 라이브러리의 사용자 지정 값을 읽는 도구를 해야 합니다.  
  
 **사용자 지정** 특성 같은 기능을가지고 있는  [사용자 지정](http://msdn.microsoft.com/library/windows/desktop/aa366766) MIDL 속성.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|비 COM `interface`,  **클래스**, `enum`s, `idl_module` 메서드, 인터페이스 멤버, 인터페이스 매개 변수를 `typedef`s,  **union**s, `struct`s|  
|**반복 가능**|예|  
|**필수 특성**|**coclass** \(클래스에서 사용 하는 경우\)|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)