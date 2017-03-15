---
title: "컴파일러 오류 C2605 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2605"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2605"
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2605
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': 이 메서드는 관리되는 클래스나 WinRT 클래스에서 예약됩니다.  
  
 특정 이름은 내부 함수용으로 컴파일러에서 예약됩니다.  자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C2605 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2605.cpp  
// compile with: /clr /c  
ref class R {  
protected:  
   void Finalize() {}   // C2605  
};  
```