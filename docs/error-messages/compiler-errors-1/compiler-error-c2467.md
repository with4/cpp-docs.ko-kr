---
title: 컴파일러 오류 C2467 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a80079c441b1ec76df6d69789d1ca3d4b09fb395
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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