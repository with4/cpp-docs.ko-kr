---
title: "컴파일러 오류 C2434 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2434
dev_langs:
- C++
helpviewer_keywords:
- C2434
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 954ef1f8db47c5cd9c420e8099cc3060ebb8a32b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2434"></a>컴파일러 오류 C2434
'symbol': __declspec (process)를 사용 하 여 선언 기호는 /clr에서 동적으로 초기화할 수 없습니다: pure 모드  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 프로세스별 변수를 동적으로 초기화할 수 없으면 **/clr: pure**합니다. 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2434 오류가 발생 합니다.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```
