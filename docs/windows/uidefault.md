---
title: "uidefault | Microsoft Docs"
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
  - "vc-attr.uidefault"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uidefault attribute"
ms.assetid: 200de0e0-2e34-40a2-bae4-8d485a62264d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uidefault
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 정보 멤버는 사용자 인터페이스에 표시 하기 위해 기본 멤버입니다.  
  
## 구문  
  
```  
  
[uidefault]  
  
```  
  
## 설명  
 **Uidefault** C\+\+ 특성을 동일한 기능을가지고 있는  [uidefault](http://msdn.microsoft.com/library/windows/desktop/aa367292) MIDL 속성입니다.  
  
## 예제  
 다음 코드 샘플을 보여 줍니다.  **uidefault**:  
  
```  
// cpp_attr_ref_uidefault.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface ICustom{  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
   [uidefault]HRESULT id0([in] long l);  
   [uidefault]HRESULT id1([in] long l);  
  
   [uidefault, propget] HRESULT get_y(int *y);  
   [uidefault, propput] HRESULT put_y(int y);  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)