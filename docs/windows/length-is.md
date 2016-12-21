---
title: "length_is | Microsoft Docs"
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
  - "vc-attr.length_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "length_is attribute"
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# length_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전송 하도록 배열 요소 수를 지정 합니다.  
  
## 구문  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### 매개 변수  
 *expression*  
 C 언어 식을 하나 이상 있습니다.  빈 인수 슬롯을 사용할 수 있습니다.  
  
## 설명  
 **Length\_is** C\+\+ 특성을 동일한 기능을가지고 있는  [length\_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL 속성입니다.  
  
## 예제  
 참조 하십시오  [first\_is](../windows/first-is.md) 의 배열 섹션을 지정 하는 방법의 예입니다.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|필드에 `struct` 또는  **union**, 매개 변수를 인터페이스를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [max\_is](../windows/max-is.md)   
 [last\_is](../windows/last-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)