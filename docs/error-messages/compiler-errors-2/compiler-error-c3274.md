---
title: "컴파일러 오류 C3274 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3274"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3274"
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3274
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

짝이 되는 try 없이 \_\_finally\/finally만 있습니다.  
  
 [\_\_finally](../../cpp/try-finally-statement.md) 또는 [finally](../../dotnet/finally.md) 문이 일치하는 `try` 없이 발견되었습니다. 이를 해결하려면 `__finally` 문을 삭제하거나 `__finally`에 대해 `try` 문을 추가합니다.  
  
 다음 샘플에서는 C3274를 생성합니다.  
  
```  
// C3274.cpp // compile with: /clr // C3274 expected using namespace System; int main() { try { try { throw gcnew ApplicationException(); } catch(...) { Console::Error->WriteLine(L"Caught an exception"); } finally { Console::WriteLine(L"In finally"); } } finally { Console::WriteLine(L"In finally"); } // Uncomment the following 3 lines to resolve. // try { //   throw gcnew ApplicationException(); // } finally { Console::WriteLine(L"In finally"); } Console::WriteLine(L"**FAIL**"); }  
```