---
title: "noncreatable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.noncreatable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "noncreatable attribute"
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# noncreatable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

자체로 인스턴스화할 수 있는 개체를 정의 합니다.  
  
## 구문  
  
```  
  
[noncreatable]  
  
```  
  
## 설명  
 **만들 수 없도록** C\+\+ 특성을 동일한 기능을가지고 있는  [만들 수 없도록](http://msdn.microsoft.com/library/windows/desktop/aa367118) MIDL 속성 및 자동으로 생성 된 전달 됩니다.컴파일러에서 IDL 파일입니다.  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작을 변경 합니다.  위의 문제 이외에 특성 또한 삽입은  [OBJECT\_ENTRY\_NON\_CREATEABLE\_EX\_AUTO](../Topic/OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO.md) 매크로.  이 매크로를 ATL 개체 외부에서 만들 수 없습니다 나타냅니다.  
  
## 예제  
  
```  
// cpp_attr_ref_noncreatable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("11111111-1111-1111-1111-111111111111")]  
__interface A   
{  
};  
  
[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]  
class CMyClass : public A   
{  
   HRESULT xx();  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)