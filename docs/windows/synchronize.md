---
title: "synchronize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.synchronize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "synchronize attribute"
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# synchronize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

대상 메서드에 대 한 액세스가 동기화합니다.  
  
## 구문  
  
```  
  
[synchronize]  
  
```  
  
## 설명  
 해당  **동기화** C\+\+ 특성 대상 메서드가 개체의 동기화에 대 한 지원을 구현 합니다.  동기화 대상 방법에 대 한 액세스를 제어 하 여 일반 자원 \(예: 클래스의 메서드\)를 사용 하는 여러 개의 개체를 수 있습니다.  
  
 이 특성에 의해 삽입 된 코드를 호출 하는 적절 한 `Lock` \(스레딩 모델에 의해 결정 됨\) 메서드는 대상 메서드의 시작 부분에.  이 메서드 종료 시 `Unlock` 자동으로 호출 됩니다.  이러한 함수에 대 한 자세한 내용은  [CComAutoThreadModule::Lock](../Topic/CComAutoThreadModule::Lock.md)  
  
 필요로 하는이 특성에  [coclass](../windows/coclass.md),  [progid](../windows/progid.md), 또는  [vi\_progid](../windows/vi-progid.md) 특성 \(또는이 중 하나를 의미 하는 다른 특성\)도 적용 될 같은 요소를 합니다.  다른 두 가지는 단일 특성을 사용 하는 경우에 자동으로 적용 됩니다.  예를 들어, 경우  **progid** 적용 된  **vi\_progid** 및  **coclass** 적용 됩니다.  
  
## 예제  
 다음 코드에 대 한 동기화를 제공는 `UpdateBalance` 메서드는 `CMyClass` 개체입니다.  
  
```  
// cpp_attr_ref_synchronize.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="SYNC")];  
  
[coclass,  
 threading(both),  
 vi_progid("MyProject.MyClass"),  
 progid("MyProject.MyClass.1"),  
 uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")  
]  
class CMyClass {  
   float m_nBalance;  
  
   [synchronize]  
   void UpdateBalance(float nAdjust) {  
      m_nBalance += nAdjust;  
   }  
};  
```  
  
## 요구 사항  
  
### 컨텍스트 특성  
  
|||  
|-|-|  
|**적용 대상**|클래스 메서드, 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|하나 이상의 다음:  **coclass**,  **progid**, 또는  **vi\_progid**.|  
|**잘못 된 특성**|없음|  
  
 속성 컨텍스트에 대 한 자세한 내용은 참조 하십시오.  [컨텍스트 특성](../windows/attribute-contexts.md).  
  
## 참고 항목  
 [COM Attributes](../windows/com-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ko-kr/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)