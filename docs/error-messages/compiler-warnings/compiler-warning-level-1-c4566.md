---
title: 컴파일러 경고 (수준 1) C4566 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8044df3a37e54585f7f3b495b99314e258934f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284227"
---
# <a name="compiler-warning-level-1-c4566"></a>컴파일러 경고(수준 1) C4566
현재 코드 페이지 (페이지)에서 유니버설 문자 이름 'char' 문자를 나타낼 수 없습니다.  
  
 현재 ANSI 코드 페이지에서 모든 유니코드 문자를 나타낼 수 있습니다.  
  
 좁은 문자열 (1 바이트 문자) (2 바이트 문자) 와이드 문자열은 반면 멀티 바이트 문자 변환 됩니다.  
  
 다음 샘플에서는 C4566 오류가 생성 됩니다.  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```