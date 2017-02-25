---
title: "first_is | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.first_is"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "first_is attribute"
ms.assetid: 89acbf56-3b38-4d44-83e8-1ce2f6f74ffd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# first_is
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전송할 첫 번째 배열 요소는 인덱스를 지정 합니다.  
  
## 구문  
  
```  
  
      [ first_is(  
   "expression"  
) ]  
```  
  
#### 매개 변수  
 *expression*  
 C 언어 식을 하나 이상 있습니다.  빈 인수 슬롯을 사용할 수 있습니다.  
  
## 설명  
 **First\_is** C\+\+ 특성을 동일한 기능을가지고 있는  [first\_is](http://msdn.microsoft.com/library/windows/desktop/aa366831) MIDL 속성입니다.  
  
## 예제  
 다음 코드 섹션에서 배열을 지정 하는 다양 한 방법을 보여 줍니다.  
  
```  
// cpp_attr_ref_first_is.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
  
[module(name="MyLib")];  
  
[object, uuid(11111111-1111-1111-1111-111111111111)]  
__interface b   
{  
   [id(0), propget, bindable, displaybind, defaultbind,   
requestedit] HRESULT get_I([out, retval]long *i);  
   HRESULT Proc1([in] short First, [in] short Last,   
[first_is(First), last_is(Last), size_is(Last-First)] char Arr1[]);   
   HRESULT Proc2([in] short First, [in] short Last,   
[last_is(First), size_is(Last)] char Arr2[]);  
};  
```  
  
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
 [last\_is](../windows/last-is.md)   
 [max\_is](../windows/max-is.md)   
 [length\_is](../windows/length-is.md)   
 [size\_is](../windows/size-is.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)