---
title: 컴파일러 경고 (수준 4) C4255 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4255
dev_langs:
- C++
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff68feb5f926a3c2cf8bbb85acfa18e8e1ecfa29
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296785"
---
# <a name="compiler-warning-level-4-c4255"></a>컴파일러 경고(수준 4) C4255
'function': 함수 프로토타입을 입력 하지 않았습니다: '()'에서 '(void)'로 변환  
  
 컴파일러는 함수에 대 한 인수의 자세한 목록을 찾을 수 없습니다. 이 경고는 C 컴파일러 에서만 합니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4255 오류가 생성 됩니다.  
  
```  
// C4255.c  
// compile with: /W4 /WX  
#pragma warning (default : 4255)  
  
void f()  { // C4255  
// try the following line instead  
//void f(void) {  
}  
  
int main(int argc, char *argv[]) {  
   f();  
}  
```