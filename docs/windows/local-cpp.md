---
title: "local (C++) | Microsoft Docs"
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
  - "vc-attr.local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "local attribute"
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# local (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스 헤더에서 사용 하는 경우 MIDL 컴파일러는 헤더 생성기로 사용할 수 있습니다.  개별 함수에서 사용 하는 경우에 대 한 없음 스텁이 생성 되는 로컬 프로시저를 지정 합니다.  
  
## 구문  
  
```  
  
[local]  
  
```  
  
## 설명  
 `local` C \+ \+ 특성을 동일한 기능을가지고 있는  [로컬](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL 특성.  
  
## 예제  
 참조 하십시오  [call\_as](../windows/call-as.md) 예를 사용 하는 방법에 대 한 `local`.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|`interface`인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|**dispinterface**|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [call\_as](../windows/call-as.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)