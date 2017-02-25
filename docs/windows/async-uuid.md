---
title: "async_uuid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.async_uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "async_uuid attribute"
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# async_uuid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동기 및 비동기 버전의 COM 인터페이스를 정의 하는 MIDL 컴파일러에 지시 하는 값을 지정 합니다.  
  
## 구문  
  
```  
  
      [async_uuid (  
   uuid  
)]  
```  
  
#### 매개 변수  
 *uuid*  
 인터페이스 버전을 식별 하는 UUID  
  
## 설명  
 **Async\_uuid** C\+\+ 특성을 동일한 기능을가지고 있는  [async\_uuid](http://msdn.microsoft.com/library/windows/desktop/aa366735) MIDL 속성입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_async_uuid.cpp  
// compile with: /LD  
#include <Windows.h>  
[module(name="Test")];  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),   
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|**이중**,  **dispinterface**|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)