---
title: "컴파일러 경고 (수준 1) C4518 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4518
dev_langs: C++
helpviewer_keywords: C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e62727eae31387c70f1b25e5e028bc6afaf3665
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4518"></a>컴파일러 경고(수준 1) C4518
'specifier': 저장소 클래스 또는 형식 지정자에 예기치 않은. 무시  
  
 다음 샘플에서는 C4518 오류가 생성 됩니다.  
  
```  
// C4518.cpp  
// compile with: /c /W1  
_declspec(dllexport) extern "C" void MyFunction();   // C4518  
  
extern "C" void MyFunction();   // OK  
```