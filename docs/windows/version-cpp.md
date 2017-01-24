---
title: "version (C++) | Microsoft Docs"
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
  - "vc-attr.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version attribute"
  - "version information, version attribute"
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# version (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

여러 개의 클래스 중에서 특정 버전을 식별합니다.  
  
## 구문  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### 매개 변수  
 *버전\(Version\)*  
 버전 번호는 coclass입니다.  지정 하지 않으면 1.0.idl 파일에 놓입니다.  
  
## 설명  
 **버전** C\+\+ 특성을 동일한 기능을가지고 있는  [버전](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL 속성, 생성 된.idl 파일에 전달 됩니다.  
  
## 예제  
 참조는  [바인딩할 수 있는](../windows/bindable.md) 샘플 사용을 예를 들어  **버전**.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스**,`struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)