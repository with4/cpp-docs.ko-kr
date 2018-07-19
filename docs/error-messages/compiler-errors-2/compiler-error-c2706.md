---
title: 컴파일러 오류 C2706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2706
dev_langs:
- C++
helpviewer_keywords:
- C2706
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92f64ddab93fb6815e3ff7a98ac39a842042bfeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232648"
---
# <a name="compiler-error-c2706"></a>컴파일러 오류 C2706
일치 하는 없이 __except를 잘못 \__try (누락 '}'에 \__try 블록?)  
  
 컴파일러는 닫는 중괄호를 찾을 수 없습니다는 `__try` 블록입니다.  
  
 다음 샘플에서는 C2706 오류가 생성 됩니다.  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```