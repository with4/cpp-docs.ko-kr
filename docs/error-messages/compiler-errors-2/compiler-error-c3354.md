---
title: "컴파일러 오류 C3354 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3354
dev_langs:
- C++
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e4fc95051f9a59db0fcb06fd4990637efda34516
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3354"></a>컴파일러 오류 C3354
'function': 대리자를 만드는 데 사용되는 함수는 'type' 반환 형식을 사용할 수 없습니다.  
  
 다음 형식은 `delegate`에 대한 반환 형식으로 부적합합니다.  
  
-   함수 포인터  
  
-   멤버 포인터  
  
-   멤버 함수에 대한 포인터  
  
-   함수에 대한 참조  
  
-   멤버 함수에 대한 참조  
  
 다음 샘플에서는 C3354를 생성합니다.  
  
```  
// C3354_2.cpp  
// compile with: /clr /c  
using namespace System;  
typedef void ( *VoidPfn )();  
  
delegate VoidPfn func(); // C3354  
// try the following line instead  
// delegate  void func();  
```  

