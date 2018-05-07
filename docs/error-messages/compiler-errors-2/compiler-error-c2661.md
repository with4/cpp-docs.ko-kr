---
title: 컴파일러 오류 C2661 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2661
dev_langs:
- C++
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcab577ae9cfd84c757ceb194d4a59ee63057993
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2661"></a>컴파일러 오류 C2661
'function': 오버 로드 된 함수가 숫자 매개 변수를 사용 합니다.  
  
 가능한 원인:  
  
1.  함수 호출에 실제 매개 변수가 잘못 되었습니다.  
  
2.  함수 선언이 없습니다.  
  
 다음 샘플에서는 C2661 오류가 생성 됩니다.  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```