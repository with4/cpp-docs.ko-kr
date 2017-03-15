---
title: "helpstringdll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstringdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstringdll attribute [C++]"
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpstringdll
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문서 문자열 \(지역화\) 조회를 수행 하는 데는 DLL의 이름을 지정 합니다.  
  
## 구문  
  
```  
  
      [ helpstringdll(  
   "string"  
) ]  
```  
  
#### 매개 변수  
 `string`  
 문서 문자열 조회를 수행 하려면 사용 하는 DLL입니다.  
  
## 설명  
 **Helpstringdll** C\+\+ 특성을 동일한 기능을가지고 있는  [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) MIDL 속성입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_helpstringdll.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib", helpstringdll="xx.dll")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI   
{  
   HRESULT xxx();  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `interface`, 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)