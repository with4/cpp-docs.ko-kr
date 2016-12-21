---
title: "importlib | Microsoft Docs"
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
  - "vc-attr.importlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importlib attribute"
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# importlib
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 형식 라이브러리에 이미 컴파일된 형식을 만들고 있는 형식 라이브러리에서 사용할 수 있도록 합니다.  
  
## 구문  
  
```  
  
        [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### 매개 변수  
 *tlb\_file*  
 현재 프로젝트의 형식 라이브러리로 가져오려는 .tlb 파일의 이름으로, 따옴표로 묶습니다.  
  
## 설명  
 **importlib** C\+\+ 특성으로 인해 `importlib` 문이 생성된 .idl 파일의 라이브러리 블록에 배치될 수 있습니다.  **importlib** 특성에는 [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL 특성과 동일한 기능이 있습니다.  
  
## 예제  
 다음 코드에서는 **importlib**의 사용 방법에 대한 예제를 보여 줍니다.  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## 요구 사항  
  
### 특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)