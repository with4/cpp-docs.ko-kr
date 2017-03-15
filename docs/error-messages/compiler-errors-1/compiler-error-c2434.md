---
title: "컴파일러 오류 C2434 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 65aac590a3282f2fd71c460d14927f5695fcdc5a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2434"></a>컴파일러 오류 C2434
'symbol': __declspec (process)를 사용 하 여 선언 기호 /clr에서 동적으로 초기화할 수 없습니다: 순수 모드  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 동적으로 아래 프로세스별 변수를 초기화할 수 없는 **/clr: pure**합니다. 자세한 내용은 참조 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2434 오류가 발생 합니다.  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```
