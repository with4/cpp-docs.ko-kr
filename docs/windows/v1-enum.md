---
title: "v1_enum | Microsoft Docs"
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
  - "vc-attr.v1_enum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "v1_enum attribute"
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# v1_enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 열거 형식 기본 16 비트 대신 32 비트 엔터티 전송 될 것을 지시 합니다.  
  
## 구문  
  
```  
  
[v1_enum]  
  
```  
  
## 설명  
 **V1\_enum** C\+\+ 특성을 동일한 기능을가지고 있는  [v1\_enum](http://msdn.microsoft.com/library/windows/desktop/aa367303) MIDL 속성입니다.  
  
## 예제  
 다음 코드는 사용을 보여 줍니다.  **v1\_enum**:  
  
```  
// cpp_attr_ref_v1_enum.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export, v1_enum]   
enum eList {   
   e1 = 1,   
   e2 = 2  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|열거 형식|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)