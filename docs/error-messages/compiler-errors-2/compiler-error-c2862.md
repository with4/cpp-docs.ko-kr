---
title: "컴파일러 오류 C2862 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2862"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2862"
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2862
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 인터페이스에는 공용 멤버만 사용할 수 있습니다.  
  
 보호된 멤버 및 전용 멤버는 다른 멤버 함수에서만 액세스할 수 있습니다.  이러한 멤버는 구현되지 않을 수 있으므로 해당 멤버는 인터페이스에서 사용되지 않습니다.  
  
 다음 샘플은 C2862를 발생시킵니다.  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```