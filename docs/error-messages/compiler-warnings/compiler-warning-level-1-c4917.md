---
title: "컴파일러 경고 (수준 1) C4917 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4917"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4917"
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4917
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declarator' : GUID는 클래스, 인터페이스 또는 네임스페이스와만 연결할 수 있습니다.  
  
 [class](../../cpp/class-cpp.md), [interface](../../cpp/interface.md) 또는 [namespace](../../misc/namespace-declaration.md) 외의 사용자 정의 구조체에는 GUID를 사용할 수 없습니다.  
  
 이 경고는 기본적으로 해제되어 있습니다.  자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md)를 참조하십시오.  
  
 다음 코드 샘플에서는 C4917 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```