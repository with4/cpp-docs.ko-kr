---
title: "out(C++) | Microsoft Docs"
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
  - "vc-attr.out"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "out 특성"
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# out(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

호출된 프로시저에서 호출하는 프로시저로 반환된\(서버에서 클라이언트로 반환된\) 포인터 매개 변수를 식별합니다.  
  
## 구문  
  
```  
  
[out]  
  
```  
  
## 설명  
 **out** C\+\+ 특성에는 [out](http://msdn.microsoft.com/library/windows/desktop/aa367136) MIDL 특성과 동일한 기능이 있습니다.  
  
## 예제  
 **out**의 샘플 사용에 대해서는 [bindable](../windows/bindable.md)에 대한 예제를 참조하세요.  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [id](../windows/id.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)