---
title: "컴파일러 오류 C2193 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2193
dev_langs: C++
helpviewer_keywords: C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e59b7e3ab659ee7760254680e51db9e2d4ca35d7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2193"></a>컴파일러 오류 C2193
'identifier': 세그먼트에 이미  
  
 함수를 사용 하 여 두 개의 서로 다른 세그먼트에 배치 된 `alloc_text` 및 `code_seg` pragma입니다.  
  
 다음 샘플에서는 C2193 오류가 생성 됩니다.  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```