---
title: "컴파일러 오류 C3554 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3554
dev_langs: C++
helpviewer_keywords: C3554
ms.assetid: aede18d5-fefc-4da9-9b69-adfe90bfa742
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 90f6e8fee5cd5e31489ff3164ce9a8220e840cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3554"></a>컴파일러 오류 C3554
'decltype'을 다른 형식 지정자와 함께 사용할 수 없습니다.  
  
 형식 지정자로 `decltype()` 키워드를 한정할 수는 없습니다. 예를 들어 다음 코드 조각은 C3554 오류를 생성합니다.  
  
```  
int x;  
unsigned decltype(x); // C3554  
```