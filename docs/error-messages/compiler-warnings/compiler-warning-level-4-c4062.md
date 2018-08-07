---
title: 컴파일러 경고 (수준 4) C4062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4062
dev_langs:
- C++
helpviewer_keywords:
- C4062
ms.assetid: 36d1c6ae-c917-4b08-bf30-2eb49ee94169
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b889fb83fa3ea3de844e4ce8c74f0a7c5d150d54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293600"
---
# <a name="compiler-warning-level-4-c4062"></a>컴파일러 경고(수준 4) C4062
열거형 'enumeration'의 switch에 있는 'identifier' 열거자가 처리되지 않습니다.  
  
 열거와 연결된 처리기가 `switch` 문에 없고, **기본** 레이블이 없습니다.  
  
 기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.  
  
 다음 샘플에서는 C4062를 생성합니다.  
  
```  
// C4062.cpp  
// compile with: /W4  
#pragma warning(default : 4062)  
enum E { a, b, c };  
void func ( E e ) {  
   switch(e) {  
      case a:  
      case b:  
      break;   // no default label  
   }   // C4062, enumerate 'c' not handled  
}  
  
int main() {  
}  
```