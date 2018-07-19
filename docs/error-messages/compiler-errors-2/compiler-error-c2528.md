---
title: 컴파일러 오류 C2528 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2528
dev_langs:
- C++
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 347330600e9b912d50522532f0c64e789e385520
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229476"
---
# <a name="compiler-error-c2528"></a>컴파일러 오류 C2528
'name': 참조에 대 한 포인터 올바르지 않습니다.  
  
 참조에 대 한 포인터를 선언할 수 없습니다. 에 대 한 포인터를 선언 하기 전에 변수를 역참조 합니다.  
  
 다음 샘플에서는 C2528 오류가 생성 됩니다.  
  
```  
// C2528.cpp  
int i;  
int &ir = i;  
int & (*irptr) = ir;    // C2528  
```