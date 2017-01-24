---
title: "컴파일러 오류 C3707 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3707"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3707"
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3707
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': dispinterface 메서드에는 dispid가 있어야 합니다.  
  
 `dispinterface` 메서드를 사용하는 경우에는 이 메서드에 `dispid`를 할당해야 합니다.  이 오류를 해결하려면 `dispinterface` 메서드에 `dispid`를 할당하십시오. 예를 들어, 아래 샘플에서는 이를 위해 메서드의 `id` 특성에서 주석 처리를 제거합니다.  자세한 내용은 [dispinterface](../../windows/dispinterface.md) 및 [id](../../windows/id.md) 특성을 참조하십시오.  
  
 다음 샘플에서는 C3707 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3707.cpp  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(name="xx")];  
[dispinterface]  
__interface IEvents : IDispatch  
{  
   HRESULT event1([in] int i);   // C3707  
   // try the following line instead  
   // [id(1)] HRESULT event1([in] int i);  
};  
  
int main() {  
}  
```