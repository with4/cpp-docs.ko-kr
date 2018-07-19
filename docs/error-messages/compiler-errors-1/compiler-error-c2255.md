---
title: 컴파일러 오류 C2255 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2255
dev_langs:
- C++
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 314d53017cf809e0ca38838cdfb3b3bb4b22437c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169607"
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