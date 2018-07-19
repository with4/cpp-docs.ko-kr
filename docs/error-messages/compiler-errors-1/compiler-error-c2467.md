---
title: 컴파일러 오류 C2467 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ed9b1b50c63852ed830c2072d7cd8fce668a671
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225645"
---
# <a name="compiler-error-c2467"></a>컴파일러 오류 C2467
익명 ' 사용자 정의 형식당 '의 잘못 된 선언  
  
 중첩 된 사용자 정의 형식이 선언 되었습니다. ANSI 호환 옵션을 사용 하는 C 소스 코드를 컴파일할 경우에 오류입니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) 사용 하도록 설정 합니다.  
  
 다음 샘플에서는 C2467 오류가 생성 됩니다.  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```