---
title: "rdx | Microsoft Docs"
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
  - "vc-attr.rdx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rdx attribute"
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# rdx
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

레지스트리 키를 만들거나 기존 레지스트리 키를 수정 합니다.  
  
## 구문  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### 매개 변수  
 `key`  
 만들거나 열 키의 이름입니다.  
  
 `valuename`\(선택 사항\)  
 설정 해야 하는 값 필드를 지정 합니다.  이 이름 값 필드에 이미 키에 없는 경우 추가 됩니다.  
  
 *regtype*  
 추가 되는 레지스트리 키의 형식입니다.  다음 중 하나가 될 수 있습니다:  **텍스트**,  **dword**,  **이진**, 또는 `CString`.  
  
## 설명  
 해당  **rdx** C\+\+ 특성을 만들거나 기존 COM 구성 요소에 대 한 레지스트리 키를 수정 합니다.  특성 대상 멤버를 구현 하는 개체에 BEGIN\_RDX\_MAP 매크로를 추가 합니다.  `RegistryDataExchange`BEGIN\_RDX\_MAP 매크로로 인해 삽입 된 함수 레지스트리 및 데이터 멤버 간에 데이터를 전송 하는 수 있습니다  
  
 과 함께이 특성을 사용할 수 있습니다에서  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 다음 중 하나를 의미 하는 다른 특성.  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|**클래스** 또는 `struct` 멤버|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 예제  
 다음 코드에서는 COM 구성 요소를 설명 하는 시스템으로 MyValue 라는 레지스트리 키를 추가 합니다.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [registration\_script](../windows/registration-script.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)