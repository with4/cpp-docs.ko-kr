---
title: "string (C++) | Microsoft Docs"
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
  - "vc-attr.string"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string attribute"
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# string (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

나타내는 있는 1 차원 `char`, `wchar_t`,  **바이트** \(또는 동등한\) 문자열로 배열 또는 이러한 배열에 대 한 포인터를 처리 해야 합니다.  
  
## 구문  
  
```  
  
[string]  
  
```  
  
## 설명  
 **문자열** C\+\+ 특성을 동일한 기능을가지고 있는  [문자열](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL 속성입니다.  
  
## 예제  
 다음 코드를 사용 하는 방법을 보여 줍니다.  **문자열** 인터페이스와 형식 정의:  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|배열 또는 배열, 인터페이스 매개 변수가 인터페이스 메서드에 대 한 포인터|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Array Attributes](../windows/array-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)