---
title: "size_is | Microsoft Docs"
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
  - "vc-attr.size_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_is attribute"
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# size_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

메모리의 크기에 대 한 크기의 포인터를 할당, 크기의 포인터와 단일\-또는 다차원 배열에 대 한 포인터의 크기를 지정 합니다.  
  
## 구문  
  
```  
  
      [ size_is(  
   "expression"  
) ]  
```  
  
#### 매개 변수  
 *expression*  
 포인터에 대 한 할당 된 메모리의 크기를 조정 합니다.  
  
## 설명  
 **Size\_is** C\+\+ 특성을 동일한 기능을가지고 있는  [size\_is](http://msdn.microsoft.com/library/windows/desktop/aa367164) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [first\_is](../windows/first-is.md) 의 배열 부분을 지정 하는 방법에 대 한.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|필드에 `struct` 또는  **union**, 매개 변수를 인터페이스를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|**max\_is**|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [first\_is](../windows/first-is.md)   
 [last\_is](../windows/last-is.md)   
 [max\_is](../windows/max-is.md)   
 [length\_is](../windows/length-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)