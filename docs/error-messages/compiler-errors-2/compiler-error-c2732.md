---
title: "컴파일러 오류 C2732 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2732
dev_langs: C++
helpviewer_keywords: C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeecaab0fd9faaa6a876aa57781160df6bb26502
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2732"></a>컴파일러 오류 C2732
링크 사양이 'function'에 대한 초기 사양과 모순됩니다.  
  
 함수가 다른 링크 지정자를 사용하여 이미 선언되었습니다.  
  
 이 오류는 링크 지정자가 다른 포함 파일로 인해 발생할 수 있습니다.  
  
 이 오류를 해결하려면 링크가 일치하도록 `extern` 문을 변경합니다. 특히 `extern "C"` 블록에서 `#include` 지시문을 줄 바꿈하지 않습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2732를 생성합니다.  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```