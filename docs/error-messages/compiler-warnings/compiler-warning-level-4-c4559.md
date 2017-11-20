---
title: "컴파일러 경고 (수준 4) C4559 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4559
dev_langs: C++
helpviewer_keywords: C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 046a3186554603d4a33b2eec78084dd76ec64e40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4559"></a>컴파일러 경고(수준 4) C4559
'function': 재정의. 함수 향상 __declspec(modifier)  
  
 함수를 다시 선언를 하거나 두 번째 정의 또는 선언은 __**declspec** 한정자 (***한정자***). 이 경고는 정보 제공용입니다. 이 경고를 해결 하려면 정의 중 하나를 삭제 합니다.  
  
 다음 샘플에서는 C4559 오류가 생성 됩니다.  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```