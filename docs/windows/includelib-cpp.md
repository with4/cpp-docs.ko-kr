---
title: "includelib (C++) | Microsoft Docs"
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
  - "vc-attr.includelib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "includelib attribute"
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# includelib (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

생성 된.idl 파일에 포함 될.idl 또는.h 파일이 됩니다.  
  
## 구문  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### 매개 변수  
 *name.idl*  
 생성 된.idl 파일의 일부로 포함 하려는.idl 파일의 이름입니다.  
  
## 설명  
 `includelib` 로 인해 생성 된.idl 파일에 다음 포함 될.idl 또는.h 파일 C\+\+ 특성은 `importlib` 문입니다.  
  
## 예제  
 다음 코드에.cpp 파일에 표시 됩니다.  
  
```  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치에|  
|**반복 가능**|예|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)