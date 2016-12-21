---
title: "library_block | Microsoft Docs"
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
  - "vc-attr.library_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "library_block attribute"
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# library_block
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IDL 라이브러리 블록 구문이 배치 됩니다.  
  
## 구문  
  
```  
  
[library_block]  
  
```  
  
## 설명  
 구문 라이브러리 블록 내에 배치 하면이 참조 여부에 관계 없이 하는 형식 라이브러리에 전달 되는 것을 확인 하십시오.  기본적으로 유일한 구문을 수정 하 여는  [coclass](../windows/coclass.md),  [dispinterface](../windows/dispinterface.md), 및  [idl\_module](../windows/idl-module.md) 특성 라이브러리 블록에 배치 합니다.  
  
## 예제  
 다음 코드에서는 사용자 지정 인터페이스 라이브러리 블록 안에 배치 됩니다.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
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
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)