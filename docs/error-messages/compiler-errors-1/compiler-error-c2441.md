---
title: "컴파일러 오류 C2441 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2441
dev_langs:
- C++
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
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
ms.openlocfilehash: 1b98c85df0db4e947ceb5722715f5d020e1ecbec
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2441"></a>컴파일러 오류 C2441
'variable': __declspec (process)를 사용 하 여 선언 기호 /clr에서 const 이어야 합니다: 순수 모드  
  
 **/clr: pure** 및 **/clr: safe** 컴파일러 옵션은 Visual Studio 2015에서는 사용 되지 않습니다.  
  
 변수는 기본적으로 응용 프로그램 도메인 별로 **/clr: pure**합니다. 표시 된 변수 `__declspec(process)` 아래 **/clr: pure** 한 응용 프로그램 도메인에서 수정 하 고 다른 언어로 읽을 경우 오류가 발생할 가능성이 높습니다.  
  
 변수는 프로세스 마다 경우 컴파일러는 따라서 `const` 아래 **/clr: 순수**, 모든 응용 프로그램 도메인 에서만 읽을 만들기.  
  
 자세한 내용은 참조 [프로세스](../../cpp/process.md) 및 [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2441 오류가 발생 합니다.  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```
