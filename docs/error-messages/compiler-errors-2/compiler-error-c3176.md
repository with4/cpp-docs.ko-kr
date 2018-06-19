---
title: 컴파일러 오류 C3176 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3176
dev_langs:
- C++
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0fedeb9861d725e9c955bb55903b49ef9fefa586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248471"
---
# <a name="compiler-error-c3176"></a>컴파일러 오류 C3176
'type': 지역 값 형식을 선언할 수 없습니다.  
  
 클래스는 전역 범위에서 값 형식으로 선언할 수만 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3176 오류가 발생 합니다.  
  
```  
// C3176.cpp  
// compile with: /clr  
int main () {  
   enum class C {};   // C3176  
}  
```