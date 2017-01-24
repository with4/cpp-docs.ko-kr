---
title: "no_injected_text | Microsoft Docs"
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
  - "vc-attr.no_injected_text"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_injected_text attribute"
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# no_injected_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컴파일러가 특성 사용으로 인해 코드를 삽입 하지 못하도록 합니다.  
  
## 구문  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### 매개 변수  
 `boolean`\(선택 사항\)  
 **true 이면** 주입, 코드가 없는 경우  **false** 코드가 삽입 될 수 있도록 합니다.  **true 이면** 기본값입니다.  
  
## 설명  
 가장 일반적인 용도  **no\_injected\_text** C\+\+ 특성을 수 여는  [\/Fx](../build/reference/fx-merge-injected-code.md) 삽입 하는 컴파일러 옵션의  **no\_injected\_text** 특성은.mrg 파일에.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)