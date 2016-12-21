---
title: "object (C++) | Microsoft Docs"
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
  - "vc-attr.object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "object attribute"
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# object (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 인터페이스를 식별합니다.  
  
## 구문  
  
```  
  
[object]  
  
```  
  
## 설명  
 인터페이스 정의 앞에 오는 경우는  **개체** 로 인해.idl 파일에 사용자 지정 인터페이스를 인터페이스 C\+\+ 특성입니다.  
  
 개체에 표시 된 모든 인터페이스에서 상속 해야 합니다  **IUnknown**.  이 조건을 만족 하는 기본 인터페이스에서 상속 하는 경우  **IUnknown**.  없음 기본 인터페이스에서 상속 하는 경우  **IUnknown**, 표시 된 인터페이스가 발생  **개체** 에서  **IUnknown**.  
  
## 예제  
 참조 하십시오  [nonbrowsable](../windows/nonbrowsable.md) 예를 사용 하는 방법에 대 한  **개체**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [dual](../windows/dual.md)   
 [dispinterface](../windows/dispinterface.md)   
 [custom](../windows/custom-cpp.md)   
 [\_\_interface](../cpp/interface.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)