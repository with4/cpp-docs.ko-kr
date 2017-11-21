---
title: "컴파일러 오류 C2634 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2634
dev_langs: C++
helpviewer_keywords: C2634
ms.assetid: 58c8f2db-ac95-4a81-9355-ef3cfb0ba7b3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2aa4d35dedc49ad4fbb226cb47790b9bedcfa6fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2634"></a>컴파일러 오류 C2634
'&class::member' : 참조 멤버에 대한 포인터가 잘못되었습니다.  
  
 참조 멤버에 대 한 포인터 선언 됩니다.  
  
 다음 샘플에서는 C2634 오류가 생성 됩니다.  
  
```  
// C2634.cpp  
int mem;  
struct S {  
   S() : rf(mem) { }  
   int &rf;  
};  
int (S::*pdm) = &S::rf;   // C2634  
```