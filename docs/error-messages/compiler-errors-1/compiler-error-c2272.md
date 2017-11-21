---
title: "컴파일러 오류 C2272 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2272
dev_langs: C++
helpviewer_keywords: C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 305b0cd510c088f4731a8430959f76bb57ee33a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2272"></a>컴파일러 오류 C2272
'function': 한정자 정적 멤버 함수에 사용할 수 없습니다  
  
 A `static` 멤버 함수는 메모리 내 모델 지정자를 사용 하 여 같은 선언 [const](../../cpp/const-cpp.md) 또는 [휘발성](../../cpp/volatile-cpp.md)에서 이러한 한정자를 사용할 수 없습니다 및 `static` 멤버 함수입니다.  
  
 다음 샘플에서는 C2272 오류가 생성 됩니다.  
  
```  
// C2272.cpp  
// compile with: /c  
class CMyClass {  
public:  
   static void func1() const volatile;   // C2272  func1 is static  
   void func2() const volatile;   // OK  
};  
```