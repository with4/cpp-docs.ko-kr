---
title: "usesgetlasterror | Microsoft Docs"
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
  - "vc-attr.usesgetlasterror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "usesgetlasterror attribute"
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# usesgetlasterror
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

호출자에 게 해당 함수를 호출 하는 동안 오류가 있으면, 다음 호출자가 다음 호출할 수 있다는 알려 `GetLastError` 오류 코드를 검색 합니다.  
  
## 구문  
  
```  
  
[usesgetlasterror]  
  
```  
  
## 설명  
 **Usesgetlasterror** C\+\+ 특성을 동일한 기능을가지고 있는  [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL 속성입니다.  
  
## 예제  
 참조는  [idl\_module](../windows/idl-module.md) 사용 하는 방법의 예는 샘플에 대 한  **usesgetlasterror**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**모듈** 특성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)