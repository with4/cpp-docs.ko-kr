---
title: "satype | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.satype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "satype attribute"
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# satype
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

데이터 형식을 지정은  **SAFEARRAY** 구조체입니다.  
  
## 구문  
  
```  
  
      [ satype(  
   data_type  
) ]  
```  
  
#### 매개 변수  
 *data\_type*  
 데이터 형식에 대 한의  **SAFEARRAY** 인터페이스 메서드를 매개 변수로 전달 되는 데이터 구조입니다.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
## 설명  
 **Satype** C\+\+ 특성의 데이터 형식 지정은  **SAFEARRAY**.  
  
> [!NOTE]
>  간접 참조 수준을 삭제 되는  **SAFEARRAY** 에서.cpp 파일에서 선언 된 생성 된.idl 파일에 대 한 포인터입니다.  
  
## 예제  
  
```  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## 참고 항목  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [id](../windows/id.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)