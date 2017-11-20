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
ms.openlocfilehash: c5ff2b3079de90efbf370082be4fee03dbfaab3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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