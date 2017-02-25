---
title: "컴파일러 오류 C2364 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2364"
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 컴파일러 오류 C2364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 사용자 지정 특성의 형식이 잘못되었습니다.  
  
 사용자 지정 특성에 대한 명명된 인수는 컴파일 타임 상수로 제한됩니다.  정수 계열 형식\(int, char 등\), System::Type^ 및 System::Object^를 예로 들 수 있습니다.  
  
## 예제  
 다음 샘플에서는 C2364 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// c2364.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute(AttributeTargets::All)]  
public ref struct ABC {  
public:  
   // Delete the following line to resolve.  
   ABC( Enum^ ) {}   // C2364  
   ABC( int ) {}   // OK  
};  
```