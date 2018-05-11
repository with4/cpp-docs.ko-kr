---
title: 컴파일러 경고 (수준 1) C4010 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ab6307a34887fe2d8a8719e20c31da9728664b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4010"></a>컴파일러 경고 (수준 1) C4010
단일 줄으로 된 주석 줄 연속 문자를 포함합니다.  
  
 도입 된 한 줄 주석을 / 백슬래시가 / (\\) 줄 연속 문자로 역할 하는 합니다. 컴파일러는 연속으로 다음 줄을 고려 하 고 주석으로 처리 합니다.  
  
 일부 구문 지향 편집기 주석으로 연속 문자를 다음 줄을 나타내지 않습니다. 구문 색이 경고를 발생 시키는 줄에서 무시 됩니다.  
  
 다음 샘플에서는 C4010 오류가 생성 됩니다.  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```