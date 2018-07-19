---
title: 컴파일러 경고 (수준 1) C4288 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c51bdc201b364d76f1692db8ee14973c90923f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276632"
---
# <a name="compiler-warning-level-1-c4288"></a>컴파일러 경고(수준 1) C4288
비표준 확장이 사용 됨: 'var': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위; 외부에서 사용 됩니다 외부 범위에 있는 선언과 충돌  
  
 로 컴파일할 때 [/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **/zc: forscope-** 에 선언 된 변수는 **에 대 한** 후 루프를 사용 하는 [에 대 한](../../cpp/for-statement-cpp.md)-루프 범위입니다. C + + 언어에 대 한 Microsoft 확장에서는이 변수를 범위에 유지 하 고 C4288 표시 변수의 첫 번째 선언 사용 되지 않습니다.  
  
 참조 [/zc: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 의 Microsoft 확장을 지정 하는 방법에 대 한 내용은 **에 대 한** /Ze로 루프입니다.  
  
 다음 샘플에서는 C4288 오류가 생성 됩니다.  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```