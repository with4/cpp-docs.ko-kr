---
title: "컴파일러 오류 C3697 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3697
dev_langs: C++
helpviewer_keywords: C3697
ms.assetid: 2d3f63c4-b7f8-421d-a7a5-2bf17fd054f9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d14bd3de0fb2ddf6c44babb10c2ec1edcb87a21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3697"></a>컴파일러 오류 C3697
'한정자':에이 한정자를 사용할 수 없습니다 ' ^'  
  
 추적 핸들 (^)를 사용할 수 없는 한정자에 적용 되었습니다.  
  
 다음 샘플에서는 C3697 오류가 생성 됩니다.  
  
```  
// C3697.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^__restrict s;   // C3697  
   String ^ s2;   // OK  
}  
```