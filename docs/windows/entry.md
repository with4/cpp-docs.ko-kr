---
title: "entry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "entry attribute"
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

내보낸된 함수 또는 상수는 모듈의 dll에서 진입점을 지정 하 여 지정 합니다.  
  
## 구문  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### 매개 변수  
 `id`  
 진입점의 ID입니다.  
  
## 설명  
 **항목** C\+\+ 특성을 동일한 기능을가지고 있는  [항목](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL 속성.  
  
## 예제  
 예제를 보려면  [idl\_module](../windows/idl-module.md) 를 사용 하는 예에 대 한  **항목**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`idl_module` 특성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)