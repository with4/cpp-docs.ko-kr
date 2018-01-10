---
title: "컴파일러 오류 C3413 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3413
dev_langs: C++
helpviewer_keywords: C3413
ms.assetid: de6c9b05-c373-4bd8-8cb0-12c2cd2e5674
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeba2eb81f2843c4478437c0292bb908210eb9ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3413"></a>컴파일러 오류 C3413
'name': 잘못된 명시적 인스턴스화입니다.  
  
 컴파일러가 잘못된 형식의 명시적 인스턴스화를 검색했습니다.  
  
 다음 샘플에서는 C3413을 생성합니다.  
  
```  
// C3413.cpp  
template  
class MyClass {};   // C3413  
```  
  
 해결 방법:  
  
```  
// C3413b.cpp  
// compile with: /c  
template <class T>  
class MyClass {};  
  
template <>  
class MyClass<int> {};  
```