---
title: 컴파일러 오류 C3286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc47c103e93fe1e4f20f5007c6688b5b6648bf32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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