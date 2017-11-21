---
title: "컴파일러 오류 C2333 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2333
dev_langs: C++
helpviewer_keywords: C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b1ed9e917ebf24509aa133dba18f9167d3a09736
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2333"></a>컴파일러 오류 C2333
'function': 함수 선언; 하는 동안 오류가 발생 했습니다. 함수 본문을 건너뜁니다.  
  
 이 오류는 해당 하는 클래스 내에 정의 된 멤버 함수에 대 한 다른 오류가 발생 한 후 발생 합니다.  
  
 다음 샘플에서는 C2333 오류가 생성 됩니다.  
  
```  
// C2333.cpp  
struct s1 {  
   s1(s1) {}   // C2333  
};  
```