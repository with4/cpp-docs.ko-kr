---
title: "컴파일러 오류 C2388 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa9f970d71be7b19551ef5029df49b696eb353e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2388"></a>컴파일러 오류 C2388
'symbol': 기호는 두 __declspec (appdomain)로 선언할 수 없습니다 및 \__declspec(process)  
  
 `appdomain` 및 `process` `__declspec` 한정자는 동일한 기호에 사용할 수 없습니다. 변수에 대한 저장소는 프로세스별 또는 응용 프로그램 도메인별로 존재합니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.  
  
 다음 샘플에서는 C2388을 생성합니다.  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```