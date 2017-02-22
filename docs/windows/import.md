---
title: "import | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.import"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "import attribute"
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# import
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

여 주 IDL에서 참조 하려는 정의 포함 하는 다른.idl,.odl, 또는 머리글 파일을 지정 합니다.  
  
## 구문  
  
```  
  
      [ import(  
   idl_file  
) ];  
```  
  
#### 매개 변수  
 `idl_file`  
 현재 프로젝트의 형식 라이브러리를 가져온된 된.idl 파일의 이름입니다.  
  
## 설명  
 **가져오기** C\+\+ 특성는 `#import` 문을 아래에 배치 하는 `import "docobj.idl"` 생성 된.idl 파일에서 문을.  **가져오기** 특성을 동일한 기능을 가진의  [가져오기](http://msdn.microsoft.com/library/windows/desktop/aa367047) MIDL 속성.  
  
 해당  **가져오기** 특성만 표시 지정한 파일이 생성 됩니다; 프로젝트의.idl 파일에  **가져오기** 특성 하지 않습니다 사용 하면 지정 된 파일에서 프로젝트의 소스 코드에서 호출 하는 구문입니다.  지정 된 파일에서 프로젝트의 소스 코드에서 호출 하는 구문에 사용할  [\# import](../preprocessor/hash-import-directive-cpp.md) 및 `embedded_idl` 특성 또는.h 파일을 포함할 수 있습니다는 `idl_file`,.h 파일이 있는 경우.  
  
## 예제  
 다음 코드는  
  
```  
// cpp_attr_ref_import.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[import(import.idl)];  
```  
  
 생성 된.idl 파일에 다음 코드를 생성합니다.  
  
```  
import "docobj.idl";  
import "import.idl";  
  
[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]  
library MyLib {  
   importlib("stdole2.tlb");  
   importlib("olepro32.dll");  
...  
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
 [importidl](../windows/importidl.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)