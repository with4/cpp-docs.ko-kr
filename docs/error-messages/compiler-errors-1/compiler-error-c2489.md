---
title: "컴파일러 오류 C2489 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2489
dev_langs: C++
helpviewer_keywords: C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 697f64be4ee5ef0b38af6d8a027b9032f38d3db6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2489"></a>컴파일러 오류 C2489
'identifier': 'naked' 함수에서 함수 범위에서 허용 되지 자동 또는 레지스터 변수를 초기화 합니다.  
  
 자세한 내용은 참조 [naked](../../cpp/naked-cpp.md)합니다.  
  
 다음 샘플에서는 C2489 오류가 생성 됩니다.  
  
```  
// C2489.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   int i = 1;   // C2489  
   register int j = 1;   // C2489  
}  
```