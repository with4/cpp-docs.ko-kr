---
title: 컴파일러 오류 C2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0fe489dbdd0934926a056bbc7e5539f40ca1ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2085"></a>컴파일러 오류 C2085
'identifier': 정식 매개 변수 목록에 없는  
  
 함수 정의에 있지만 형식 매개 변수 목록에 없는 식별자 선언 되었습니다. (ANSI C에만 해당)  
  
 다음 샘플에서는 C2085 오류가 생성 됩니다.  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 해결 방법:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 세미콜론 누락 된 `func1()` 하므로 프로토타입이 아니라 함수 정의 처럼 보이는 `main` 내에 정의 된 `func1()`, 식별자에 대 한 오류 c2085 `main`합니다.