---
title: "컴파일러 오류 C2710 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2710
dev_langs: C++
helpviewer_keywords: C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5bb6349bf6efb8c63b68c78644343ace5dc07e67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2710"></a>컴파일러 오류 C2710
'construct': '__declspec(modifier)' 포인터를 반환 하는 함수에만 적용할 수 있습니다  
  
 반환 값이 함수는 있는 유일한 구문 `modifier` 적용 될 수 있습니다.  
  
 다음 샘플에서는 C2710 오류가 생성 됩니다.  
  
```  
// C2710.cpp  
__declspec(restrict) void f();   // C2710  
// try the following line instead  
__declspec(restrict) int * g();  
```