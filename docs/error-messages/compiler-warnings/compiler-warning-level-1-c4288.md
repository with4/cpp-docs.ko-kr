---
title: "컴파일러 경고 (수준 1) C4288 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4288
dev_langs: C++
helpviewer_keywords: C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a10a7573df5986ed20475b34208a1e0f301d9bb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4288"></a>컴파일러 경고(수준 1) C4288
비표준 확장이 사용 됨: 'var': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위; 외부에서 사용 됩니다 외부 범위에 있는 선언과 충돌  
  
 로 컴파일할 때 [/Ze](../../build/reference/za-ze-disable-language-extensions.md) 및 **/zc: forscope-**에 선언 된 변수는 **에 대 한** 후 루프를 사용 하는 [에 대 한](../../cpp/for-statement-cpp.md)-루프 범위입니다. C + + 언어에 대 한 Microsoft 확장에서는이 변수를 범위에 유지 하 고 C4288 표시 변수의 첫 번째 선언 사용 되지 않습니다.  
  
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