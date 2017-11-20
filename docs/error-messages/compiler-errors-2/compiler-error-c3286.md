---
title: "컴파일러 오류 C3286 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3286
dev_langs: C++
helpviewer_keywords: C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ea704fce0aebd3ffa83410104b38ceb5d359a6c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3286"></a>컴파일러 오류 C3286  
  
> '*지정자*': 반복 변수에 저장소 클래스 지정자를 사용할 수 없습니다  
  
반복 변수에는 저장소 클래스를 지정할 수 없습니다. 자세한 내용은 참조 [저장소 클래스 (c + +)](../../cpp/storage-classes-cpp.md) 및 [각 항목에 대해에서](../../dotnet/for-each-in.md)합니다.  
  
## <a name="example"></a>예제  
  
다음 샘플에서는 c 3286, 오류가 발생 하는 경우 및 올바른 사용법을 보여 줍니다.  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```