---
title: "컴파일러 오류 C2516 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2516
dev_langs:
- C++
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5df8d59b8e812e2c3eeb450f4ea811b6c837f085
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2516"></a>컴파일러 오류 C2516
'name': 올바른 기본 클래스가 아닙니다.  
  
 에 정의 된 형식 이름에서 파생 된 클래스는 `typedef` 문.  
  
 다음 샘플에서는 C2516 오류가 생성 됩니다.  
  
```  
// C2516.cpp  
typedef unsigned long ulong;  
class C : public ulong {}; // C2516  
```