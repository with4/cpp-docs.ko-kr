---
title: 컴파일러 경고 (수준 3) C4310 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4310
dev_langs:
- C++
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd3ab8ba6eb9175ad3f567408faa1f78c09a6f6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33303071"
---
# <a name="compiler-warning-level-3-c4310"></a>컴파일러 경고(수준 3) C4310
캐스트 상수 값을 잘립니다.  
  
 상수 값을 더 작은 형식으로 캐스팅 됩니다. 컴파일러가 캐스트 데이터를 자릅니다를 수행 합니다. 다음 샘플에서는 C4310 오류가 생성 됩니다.  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```