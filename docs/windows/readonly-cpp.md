---
title: "readonly(C++) | Microsoft Docs"
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
  - "vc-attr.readonly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "readonly 특성"
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# readonly(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 멤버에 대한 할당을 금지합니다.  
  
## 구문  
  
```  
  
[readonly]  
  
```  
  
## 설명  
 **readonly** C\+\+ 특성에는 [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) MIDL 특성과 동일한 기능이 있습니다.  
  
 메서드 매개 변수의 수정을 금지하려면 [in](../windows/in-cpp.md) 특성을 사용합니다.  
  
## 예제  
 다음 코드에서는 **readonly** 특성의 사용을 보여줍니다.  
  
```  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
};  
```  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)