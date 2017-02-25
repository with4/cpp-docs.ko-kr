---
title: "appobject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.appobject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "appobject attribute"
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# appobject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Coclass는 전체.exe 응용 프로그램에 연결 되 고 함수 및 속성은 coclass의이에서 전체적으로 사용할 수 있는지 나타냅니다을 응용 프로그램 개체 식별  [형식 라이브러리](../mfc/automation-clients-using-type-libraries.md).  
  
## 구문  
  
```  
  
[appobject]  
  
```  
  
## 설명  
 **Appobject** C\+\+ 특성을 동일한 기능을가지고 있는  [appobject](http://msdn.microsoft.com/library/windows/desktop/aa366726) MIDL 속성입니다.  
  
## 예제  
 간단한 클래스 정의 포함 하는 특성 블록에서 앞에 다음 코드를 보여 줍니다.  **appobject**:  
  
```  
// cpp_attr_ref_appobject.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];  
  
[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]  
__interface ICustom {};  
  
[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]  
class A : public ICustom {  
   int i;  
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
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)