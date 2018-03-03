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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 848a0063cc50eefc76a7c635f7a6f69a0a8b996f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2434"></a>컴파일러 오류 C2434
'symbol': __declspec (process)를 사용 하 여 선언 기호는 /clr에서 동적으로 초기화할 수 없습니다: pure 모드  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 프로세스별 변수를 동적으로 초기화할 수 없으면 **/clr: pure**합니다. 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2434 오류가 발생 합니다.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```