---
title: 컴파일러 오류 c 2780 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2780
dev_langs:
- C++
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fba3d16284e8f56dd3583cb73d4b8fec56222a38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232727"
---
# <a name="compiler-error-c2780"></a>컴파일러 오류 c 2780
'declaration' : 인수가 N개 있어야 하는데 M개를 사용했습니다.  
  
 함수 템플릿에 인수가 너무 적거나 너무 많습니다.  
  
 다음 샘플에서는 C2780을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```