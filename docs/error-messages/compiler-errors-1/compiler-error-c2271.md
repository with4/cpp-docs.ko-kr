---
title: "컴파일러 오류 C2271 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2271
dev_langs: C++
helpviewer_keywords: C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 59a4057d9d52df1a8a1b4b629dc3a13ae4c4c7a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2271"></a>컴파일러 오류 C2271
'operator': 새/삭제는 형식 목록 한정자를 사용할 수 없습니다  
  
 연산자 (`new` 또는 `delete`) 메모리 내 모델 지정자로 선언 합니다.  
  
 다음 샘플에서는 C2271 오류가 생성 됩니다.  
  
```  
// C2271.cpp  
// compile with: /c  
void* operator new(size_t) const {   // C2271  
// try the following line instead  
// void* operator new(size_t) {  
   return 0;  
}  
  
struct X {  
   static void* operator new(size_t) const;   // C2271  
   // try the following line instead  
   // void * X::operator new(size_t) const;   // static member operator new  
};  
```