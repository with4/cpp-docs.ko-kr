---
title: "lcid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.lcid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LCID attribute"
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# lcid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

로캘 식별자를 함수에 전달할 수 있습니다.  
  
## 구문  
  
```  
  
[lcid]  
  
```  
  
## 설명  
 **Lcid** 구현 기능을 C\+\+ 특성은  [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) MIDL 속성입니다.  라이브러리 블록에 대 한 로케일을 구현 하려는 경우에 사용의  **lcid \=**`lcid` 매개 변수는  [모듈](../windows/module-cpp.md) 특성.  
  
## 예제  
  
```  
// cpp_attr_ref_lcid.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
typedef long HRESULT;  
  
[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]  
__interface IStatic {  
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 자세한 내용은  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)