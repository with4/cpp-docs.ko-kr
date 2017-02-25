---
title: "call_as | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.call_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call_as attribute"
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# call_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

수는  [로컬](../windows/local-cpp.md) 함수에서 원격 함수를 호출 하면 로컬 함수가 호출 되는 원격 함수에 매핑해야 합니다.  
  
## 구문  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### 매개 변수  
 *함수*  
 원하는 원격 함수를 호출 하면 호출 하는 로컬 함수입니다.  
  
## 설명  
 **Call\_as** C\+\+ 특성을 동일한 기능을가지고 있는  [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL 속성입니다.  
  
## 예제  
 다음 코드에서는 사용 방법을 보여 줍니다.  **call\_as** 원격 가능 하지 않을 기능을 매핑하는 데 \(**f1**\) 원격화 할 수 있는 기능 \(**Remf1**\):  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)