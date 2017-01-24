---
title: "importidl | Microsoft Docs"
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
  - "vc-attr.importidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importidl attribute"
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# importidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된.idl 파일 생성 된.idl 파일에 삽입합니다.  
  
## 구문  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### 매개 변수  
 `idl_file`  
 생성 되는 응용 프로그램에 대 한.idl 파일을 병합 하려면.idl 파일의 이름을 식별 합니다.  
  
## 설명  
 **Importidl** C\+\+ 특성 섹션에서 라이브러리 블록 외부에 배치 \(에 `idl_file`\) 프로그램의 생성 된.idl 파일 라이브러리 구역에 \(에 `idl_file`\) 라이브러리에.idl 파일 섹션의 프로그램을 생성 합니다.  
  
 사용할 수 있습니다  **importidl**, 예를 들어, 생성 된.idl 파일을 손 코딩 된.idl 파일을 사용 하려는 경우.  
  
## 예제  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [import](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)