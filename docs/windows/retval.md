---
title: "retval | Microsoft Docs"
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
  - "vc-attr.retval"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "retval attribute"
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# retval
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

멤버의 반환 값을 받는 매개 변수를 지정 합니다.  
  
## 구문  
  
```  
  
[retval]  
  
```  
  
## 설명  
 **Retval** C\+\+ 특성을 동일한 기능을가지고 있는  [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL 속성입니다.  
  
 **retval** 의 마지막 인수는 함수 선언에 나타나야 합니다.  
  
## 예제  
 예제를 보려면  [바인딩할 수 있는](../windows/bindable.md) 의 샘플 사용에 대 한  **retval**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|**out**|  
|**잘못 된 특성**|**in**|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)