---
title: "컴파일러 오류 C3285 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3285
dev_langs:
- C++
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83b1d08d9afc054f5f90190a0677a11fcfc18b53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3285"></a>컴파일러 오류 C3285
for each 문은 'type' 형식의 변수에 사용할 수 없습니다.  
  
 `for each` 문은 배열 또는 개체 컬렉션의 각 요소에 대해 포함된 문 그룹을 반복합니다.  
  
 자세한 내용은 [for each, in](../../dotnet/for-each-in.md) 를 참조하세요.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3285를 생성합니다.  
  
```  
// C3285.cpp  
// compile with: /clr  
int main() {  
   for each (int i in 0) {}   // C3285   
  
   array<int> ^p = { 1, 2, 3 };  
   for each (int j in p) {}   // OK  
}  
```