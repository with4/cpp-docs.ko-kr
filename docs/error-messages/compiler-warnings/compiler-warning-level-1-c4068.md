---
title: "컴파일러 경고 (수준 1) C4068 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4068
dev_langs:
- C++
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4dd3b5f58027ab855f89fbb008c344436ca316ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4068"></a>컴파일러 경고(수준 1) C4068
알 수 없는 pragma입니다.  
  
 컴파일러가 인식할 수 없는 [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)를 무시했습니다. 사용하는 컴파일러에서 **pragma** 가 허용되는지 확인합니다. 다음 샘플에서는 C4068을 생성합니다.  
  
```  
// C4068.cpp  
// compile with: /W1  
#pragma NotAValidPragmaName   // C4068, use valid name to resolve  
int main()  
{  
}  
```