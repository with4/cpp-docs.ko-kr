---
title: "컴파일러 오류 C2423 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2423
dev_langs:
- C++
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52491ec758f94c7c28d0a4013cd65850b39092dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2423"></a>컴파일러 오류 C2423
'number': 잘못 된 크기 조정  
  
 인라인 어셈블리 코드 레지스터 크기를 조정 하려면 1, 2, 4 또는 8 이외의 번호를 사용 합니다.  
  
 다음 샘플에서는 C2423 오류가 생성 됩니다.  
  
```  
// C2423.cpp  
// processor: x86  
int main() {  
   _asm {  
      lea EAX, [EAX*3]   // C2423  
      lea EAX, [EAX+EAX*2]   // OK  
   }  
}  
```