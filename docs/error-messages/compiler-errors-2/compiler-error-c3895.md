---
title: "컴파일러 오류 C3895 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3895
dev_langs: C++
helpviewer_keywords: C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75bd27d44ed74817cc23e6b58f036742d2d1979b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3895"></a>컴파일러 오류 C3895
'var': 형식 데이터 멤버 'volatile' 일 수 없습니다  
  
 예를 들어 데이터 멤버의 특정 종류 [리터럴](../../windows/literal-cpp-component-extensions.md) 또는 [initonly](../../dotnet/initonly-cpp-cli.md), 될 수 없습니다 [휘발성](../../cpp/volatile-cpp.md)합니다.  
  
 다음 샘플에서는 C3895 오류가 생성 됩니다.  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```