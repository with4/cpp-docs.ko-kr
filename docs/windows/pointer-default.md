---
title: "pointer_default | Microsoft Docs"
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
  - "vc-attr.pointer_default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_default attribute"
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pointer_default
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

매개 변수 목록에 표시 되는 최상위 포인터를 제외한 모든 포인터에 대 한 기본 포인터 특성을 지정 합니다.  
  
## 구문  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### 매개 변수  
 *value*  
 포인터 형식에 설명 하는 값:  **ptr**, `ref`, 또는  **고유**.  
  
## 설명  
 **Pointer\_default**  C\+\+ 특성을 동일한 기능을가지고 있는  [pointer\_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [defaultvalue](../windows/defaultvalue.md) 의 샘플 사용에 대 한  **pointer\_default**.  
  
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
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)