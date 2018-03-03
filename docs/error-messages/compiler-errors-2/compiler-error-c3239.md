---
title: "컴파일러 오류 C3239 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3239
dev_langs:
- C++
helpviewer_keywords:
- C3239
ms.assetid: 22a518b7-020f-4f3c-9963-a094667fd1ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e356befb8fa8492afd888a2d534f4c1e2c018c5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3239"></a>컴파일러 오류 C3239
'type': 공용 언어 런타임에서 interior/pin 포인터에 대한 pointer는 허용되지 않습니다.  
  
 컴파일러가 잘못된 형식을 찾았습니다.  
  
 다음 샘플에서는 C3229를 생성합니다.  
  
```  
// C3239.cpp  
// compile with: /clr  
int main() {  
   interior_ptr<int>* pip0;   // C3239  
  
   // OK  
   int * pip1;  
   interior_ptr<int> pip2;  
   int ** pip;  
}  
```