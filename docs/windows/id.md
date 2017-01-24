---
title: "id | Microsoft Docs"
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
  - "vc-attr.id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "id attribute"
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 `dispid` 멤버 함수 \(속성 또는 메서드가 인터페이스 또는 dispinterface에\)에 대 한 매개 변수입니다.  
  
## 구문  
  
```  
  
      [ id(  
   dispid  
) ]  
```  
  
#### 매개 변수  
 `dispid`  
 인터페이스 메서드의 디스패치 ID입니다.  
  
## 설명  
 **Id** C\+\+ 특성을 동일한 기능을가지고 있는  [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [바인딩할 수 있는](../windows/bindable.md) 예를 사용 하는 방법에 대 한  **id**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [아웃](../windows/out-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)