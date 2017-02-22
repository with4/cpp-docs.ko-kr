---
title: "helpfile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpfile attribute"
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpfile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 라이브러리에 대 한 도움말 파일의 이름을 설정 합니다.  
  
## 구문  
  
```  
  
      [ helpfile(  
   "filename"  
) ]  
```  
  
#### 매개 변수  
 *filename*  
 도움말 항목에 들어 있는 파일의 이름입니다.  
  
## 설명  
 **도움말 파일** C\+\+ 특성을 동일한 기능을가지고 있는  [도움말 파일](http://msdn.microsoft.com/library/windows/desktop/aa366853) MIDL 속성입니다.  
  
## 예제  
 예제를 보려면  [모듈](../windows/module-cpp.md) 예를 사용 하는 방법에 대 한  **도움말 파일**.  
  
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
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)