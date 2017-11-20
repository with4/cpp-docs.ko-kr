---
title: "컴파일러 경고 C4936 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4936
dev_langs: C++
helpviewer_keywords: C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4342c749c5db4d66f206209a146ad7d7aef7041
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4936"></a>컴파일러 경고 C4936
/clr 또는 /clr:pure를 지정하여 컴파일한 경우에만 이 __declspec를 사용할 수 있습니다.  
  
 **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않습니다.  
  
 `__declspec` 한정자가 사용되었지만 해당 `__declspec` 한정자는 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 옵션 중 하나로 컴파일된 경우에만 유효합니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.  
  
 C4936은 항상 오류로 실행됩니다.  [warning](../../preprocessor/warning.md) pragma를 사용하여 C4936을 해제할 수 있습니다.  
  
 다음 샘플에서는 C4936을 생성합니다.  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```