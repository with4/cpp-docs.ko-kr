---
title: "include (C++) | Microsoft Docs"
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
  - "vc-attr.include"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include attribute"
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# include (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

생성 된.idl 파일에 포함 시킬 헤더 파일을 지정 합니다.  
  
## 구문  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### 매개 변수  
 *header\_file*  
 생성 된.idl 파일에 포함 된 파일의 이름입니다.  
  
## 설명  
 **포함** C\+\+ 특성는 `#include` 문을 아래에 배치 하는 `import "docobj.idl"` 생성 된.idl 파일에서 문을.  
  
 **포함** C\+\+ 특성을 동일한 기능을가지고 있는  [포함](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL 특성.  
  
## 예제  
 다음 코드를 사용 하는 방법의 예를 보여 줍니다.  **포함**.  문에 \# include만이 때 파일 include.h 포함 되어 있습니다.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)