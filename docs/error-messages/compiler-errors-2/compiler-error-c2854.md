---
title: "컴파일러 오류 C2854 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2854
dev_langs: C++
helpviewer_keywords: C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f8423af7be34d431ab8ace8ca512d857611c6c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2854"></a>컴파일러 오류 C2854
#pragma hdrstop에 구문 오류가  
  
 `#pragma hdrstop` 이름이 잘못 되었습니다. Pragma는 괄호 및 따옴표 선택적 파일 이름이 올 수 있습니다.  
  
 다음 샘플에서는 C2854 오류가 생성 됩니다.  
  
```  
// C2854.cpp  
// compile with: /c  
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854  
// try the following line instead  
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )  
```