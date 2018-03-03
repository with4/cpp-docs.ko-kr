---
title: "컴파일러 오류 C2255 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2255
dev_langs:
- C++
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ca5f2a33b07ff0b78f12c20f528f1d9b6c3c20d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2255"></a>컴파일러 오류 C2255
'element': 클래스 정의 외부에서 사용할 수 없습니다.  
  
 예를 들어 비멤버 함수를 `friend`로 선언했습니다.  
  
 다음 샘플에서는 C2255를 생성합니다.  
  
```  
// C2255.cpp  
// compile with: /c  
class A {  
private:  
   void func1();  
   friend void func2();  
};  
  
friend void func1() {}   // C2255  
void func2(){}  
```