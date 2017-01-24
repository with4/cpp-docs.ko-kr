---
title: "컴파일러 오류 C2778 | Microsoft Docs"
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
  - "C2778"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2778"
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2778
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_declspec\(uuid\(\)\)에서 GUID 형식이 잘못되었습니다.  
  
 [uuid](../../cpp/uuid-cpp.md) 확장 특성에 잘못된 GUID가 제공되었습니다.  
  
 GUID는 다음 형식을 사용하는 16진 문자열이어야 합니다.  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 `uuid` 확장 특성은 중괄호 구분 기호를 포함하거나 포함하지 않은 채로, [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589)에 의해 인식되는 문자열을 허용합니다.  
  
 다음 샘플에서는 C2778 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```