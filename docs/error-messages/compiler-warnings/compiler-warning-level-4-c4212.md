---
title: "컴파일러 경고 (수준 4) C4212 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4212
dev_langs: C++
helpviewer_keywords: C4212
ms.assetid: df781ea1-182d-4f9f-9a31-55b6ce80c711
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9573a6e29ce20a87fb75aa5810ebf4d696695a45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4212"></a>컴파일러 경고(수준 4) C4212
비표준 확장이 사용 됨: 줄임표를 사용 하는 함수 선언  
  
 함수 프로토타입에 인수의 변수 수 있습니다. 함수 정의 그렇지 않습니다.  
  
 다음 샘플에서는 C4212 오류가 생성 됩니다.  
  
```  
// C4212.c  
// compile with: /W4 /Ze /c  
void f(int , ...);  
void f(int i, int j) {}  
```