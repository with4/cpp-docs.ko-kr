---
title: "컴파일러 오류 C2190 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2190
dev_langs:
- C++
helpviewer_keywords:
- C2190
ms.assetid: 34e15f85-d979-4948-80fc-46c414508a70
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 647c17808c1a91fb06923fd8601ee77c17732a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2190"></a>컴파일러 오류 C2190
첫 번째 매개 변수 목록이 둘째 보다 깁니다.  
  
 C 함수를 한 번 더 짧은 매개 변수 목록 사용 하 여 선언 되었습니다. C에서 오버 로드 된 함수를 지원 하지 않습니다.  
  
 다음 샘플에서는 C2190 오류가 생성 됩니다.  
  
```  
// C2190.c  
// compile with: /Za /c  
void func( int, float );  
void func( int  );   // C2190, different parameter list  
void func2( int  );   // OK  
```