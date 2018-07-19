---
title: 컴파일러 오류 C2563 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85a4de195c681ce8d11b789a9aca102629cc2bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228596"
---
# <a name="compiler-error-c2563"></a>컴파일러 오류 C2563
형식 매개 변수 목록에서 일치 하지 않습니다.  
  
 함수 (또는 함수에 대 한 포인터)의 형식 매개 변수 목록에 다른 함수 (또는 멤버 함수에 대 한 포인터)의 인수와 일치 하지 않습니다. 결과적으로, 함수 또는 포인터의 할당을 만들 수 없습니다.  
  
 다음 샘플에서는 C2563 오류가 생성 됩니다.  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```