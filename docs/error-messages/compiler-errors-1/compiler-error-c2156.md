---
title: 컴파일러 오류 C2156 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2156
dev_langs:
- C++
helpviewer_keywords:
- C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 288757f93e0cf7c478fae739f106482b5ba8a016
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2156"></a>컴파일러 오류 C2156
pragma는 함수 외부에 있어야 합니다.  
  
 전역 수준(함수 본문 외부)에서 지정해야 하는 pragma가 함수 내에 있습니다.  
  
 다음 샘플에서는 C2156을 생성합니다.  
  
```  
// C2156.cpp  
#pragma optimize( "l", on )   // OK  
int main() {  
   #pragma optimize( "l", on )   // C2156  
}  
```