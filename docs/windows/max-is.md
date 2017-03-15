---
title: "max_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.max_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_is attribute"
ms.assetid: 7c851f5c-6649-4d77-a792-247c37d8f560
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# max_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

올바른 배열 인덱스에 대 한 최대 값을 지정합니다.  
  
## 구문  
  
```  
  
      [ max_is(  
   "expression"  
) ]  
```  
  
#### 매개 변수  
 *expression*  
 C 언어 식을 하나 이상 있습니다.  빈 인수 슬롯을 사용할 수 있습니다.  
  
## 설명  
 **Max\_is** C\+\+ 특성을 동일한 기능을가지고 있는  [max\_is](http://msdn.microsoft.com/library/windows/desktop/aa367074) MIDL 속성입니다.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|필드에 `struct` 또는  **union**, 매개 변수를 인터페이스를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|**size\_is**|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 예제  
 참조 하십시오  [first\_is](../windows/first-is.md) 의 배열 섹션을 지정 하는 방법의 예입니다.  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)