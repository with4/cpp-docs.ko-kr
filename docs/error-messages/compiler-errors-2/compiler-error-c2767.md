---
title: "컴파일러 오류 C2767 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2767
dev_langs: C++
helpviewer_keywords: C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8fe74f9374a6fb74a514fd2655b2e1dbadf02639
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2767"></a>컴파일러 오류 C2767
관리 되는 또는 WinRTarray 차원 불일치: N 인수가 필요한 데 M 제공  
  
 WinRT 또는 관리되는 배열 선언의 형식이 잘못되었습니다. 자세한 내용은 [배열](../../windows/arrays-cpp-component-extensions.md)을 참조하세요.  
  
 다음 샘플에서는 C2767 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```