---
title: "helpcontext | Microsoft Docs"
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
  - "vc-attr.helpcontext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpcontext attribute"
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# helpcontext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 도움말 파일에서이 요소에 대 한 정보를 보기 수 있는 컨텍스트 ID를 지정 합니다.  
  
## 구문  
  
```  
  
      [ helpcontext(  
   id  
) ]  
```  
  
#### 매개 변수  
 `id`  
 도움말 항목의 컨텍스트 ID를 지정 합니다.  참조 하십시오 [HTML 도움말: 프로그램에 대한 상황에 맞는 도움말](../mfc/html-help-context-sensitive-help-for-your-programs.md) 컨텍스트 Id에 대 한 자세한 내용은.  
  
## 설명  
 **가 helpcontext** C\+\+ 특성을 동일한 기능을가지고 있는  [가 helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [defaultvalue](../windows/defaultvalue.md) 예를 사용 하는 방법에 대 한  **가 helpcontext**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface` `typedef`,  **클래스**, 메서드, 속성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [helpfile](../windows/helpfile.md)   
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)