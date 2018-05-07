---
title: 컴파일러 오류 C2448 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc62d7aeba0a128c9b736586e6c1502227de717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2448"></a>컴파일러 오류 C2448
'identifier': 함수 스타일 이니셜라이저가 함수 정의 것 같습니다.  
  
 함수 정의가 잘못 되었습니다.  
  
 이 오류는 이전 스타일 C 언어 형식 목록을 사용 하 여 발생할 수 있습니다.  
  
 다음 샘플에서는 C2448 오류가 생성 됩니다.  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```