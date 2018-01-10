---
title: "컴파일러 오류 C3898 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3898
dev_langs: C++
helpviewer_keywords: C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b961c7eb788d1938263025e442a3e336a8ce3567
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3898"></a>컴파일러 오류 C3898
'var': 형식 데이터 멤버 관리 되는 형식의 멤버만 될 수 있습니다  
  
 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 기본 클래스에서 선언 되었습니다.  `initonly` 데이터 멤버는 CLR 클래스 에서만 선언할 수 있습니다.  
  
 다음 샘플에서는 C3898 오류가 생성 됩니다.  
  
```  
// C3898.cpp  
// compile with: /clr  
struct Y1 {  
   initonly  
   static int data_var = 9;   // C3898  
};  
```  
  
 해결 방법:  
  
```  
// C3898b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int data_var = 9;  
};  
```