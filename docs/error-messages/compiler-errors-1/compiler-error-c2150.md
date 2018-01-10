---
title: "컴파일러 오류 C2150 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2150
dev_langs: C++
helpviewer_keywords: C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d31a8767f05ba8c58e07ffbabed4e7a96a919e6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2150"></a>컴파일러 오류 C2150
  
> '*식별자*': 비트 필드 형식은 'int', 'signed int' 또는 'unsigned int' 해야 합니다.  
  
 비트 필드에 대 한 기본 형식 되어야 할 `int`, `signed int`, 또는 `unsigned int`합니다.  
  
## <a name="example"></a>예  
  
 이 샘플에서는 c 2150을 발생할 수 있는 방법 및 해결 방법 보여 줍니다.  
  
```cpp  
// C2150.cpp  
// compile with: /c  
struct A {  
   float a : 8;    // C2150  
   int i : 8;      // OK  
};  
```