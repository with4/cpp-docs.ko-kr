---
title: "컴파일러 경고 (수준 1) C4129 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4129
dev_langs: C++
helpviewer_keywords: C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1efeca1e597af8e7f96b2854fcbcfc49b000009a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4129"></a>컴파일러 경고 (수준 1) C4129
'character': 문자 이스케이프 시퀀스를 인식할 수 없습니다  
  
 `character` 백슬래시 다음 (\\)에 문자 또는 문자열 상수는 유효한 이스케이프 시퀀스도 인식 되지 않습니다. 백슬래시는 무시 되 고 인쇄 되지 않습니다. 백슬래시 뒤의 문자 인쇄 됩니다.  
  
 단일 백슬래시를 인쇄 하려면 이중 백슬래시를 지정 합니다. (\\\\).  
  
 C + + 표준 2.13.2 섹션에는 이스케이프 시퀀스를 설명합니다.  
  
 다음 샘플에서는 C4129 오류가 생성 됩니다.  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```