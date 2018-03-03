---
title: "컴파일러 오류 C2449 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2449
dev_langs:
- C++
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2736462f86446ada205d43afdbde63374e689254
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2449"></a>컴파일러 오류 C2449
찾을 ' {' 파일 범위 (가)  
  
 파일 범위에는 중괄호가 있습니다.  
  
 이 오류는 함수 헤더와 함수 정의의 여는 중괄호 사이 세미콜론으로 발생할 수 있습니다.  
  
 다음 샘플에서는 C2499 오류가 생성 됩니다.  
  
```  
// C2449.c  
// compile with: /c  
void __stdcall func(void) {}   // OK  
void __stdcall func(void);  // extra semicolon on this line  
{                         // C2449 detected here  
```