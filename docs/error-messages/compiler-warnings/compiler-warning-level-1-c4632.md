---
title: "컴파일러 경고 (수준 1) C4632 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4632
dev_langs: C++
helpviewer_keywords: C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 34f6af06499dd57bda8bf07954db44cd76e116fb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4632"></a>컴파일러 경고(수준 1) C4632
XML 문서 주석: file-액세스 거부: 이유  
  
 .Xdc 파일의 경로입니다 (`file`).xdc 파일이 생성 되지 및 올바르지 않습니다.  
  
 다음 샘플에서는 C4632 오류가 생성 됩니다.  
  
```  
// C4632.cpp  
// compile with: /clr /docv:\\falsedir /LD /W1  
// C4632 expected  
  
/// Text for class MyClass.  
public ref class MyClass {};  
```