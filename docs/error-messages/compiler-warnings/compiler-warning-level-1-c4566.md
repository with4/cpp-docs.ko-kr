---
title: "컴파일러 경고 (수준 1) C4566 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4566
dev_langs:
- C++
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22a53aae49f025c8d05beb3b491288e5c82345a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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