---
title: "컴파일러 경고 C4956 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: 9
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 782735be55c043482679740afa9571ba7b29dfc4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-c4956"></a>컴파일러 경고 C4956
'type': 이 형식은 확인할 수 없습니다.  
  
 이 경고는 발생 때 [/clr: safe](../../build/reference/clr-common-language-runtime-compilation.md) 지정 된 코드를 확인할 수 없는 형식을 포함 합니다.  
  
 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
 이 경고는 오류로 발생 하며를 비활성화할 수 있습니다는 [경고](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션입니다.  
  
 다음 샘플에서는 C4956을 생성합니다.  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```
