---
title: "컴파일러 오류 C2528 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2528
dev_langs:
- C++
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 953e3b0c7af59b3358ad2c0b0743cc8d214bf91e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2528"></a>컴파일러 오류 C2528
'name': 참조에 대 한 포인터 올바르지 않습니다.  
  
 참조에 대 한 포인터를 선언할 수 없습니다. 에 대 한 포인터를 선언 하기 전에 변수를 역참조 합니다.  
  
 다음 샘플에서는 C2528 오류가 생성 됩니다.  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```