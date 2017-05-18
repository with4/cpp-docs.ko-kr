---
title: "컴파일러 경고 C4936 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4936
dev_langs:
- C++
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 58d702067c186eeeea94768a03836b64577961ca
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4936"></a>컴파일러 경고 C4936
/clr 또는 /clr:pure를 지정하여 컴파일한 경우에만 이 __declspec를 사용할 수 있습니다.  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 A `__declspec` 한정자가 사용 된 것 같지만 `__declspec` 한정자만 유효 중 하나를 사용 하 여 컴파일된 경우는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션입니다.  
  
 자세한 내용은 참조 [appdomain](../../cpp/appdomain.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
 C4936은 항상 오류로 실행됩니다.  와 C4936를 비활성화할 수는 [경고](../../preprocessor/warning.md) pragma 합니다.  
  
 다음 샘플에서는 C4936을 생성합니다.  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```
