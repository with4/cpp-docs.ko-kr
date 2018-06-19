---
title: 컴파일러 경고 (수준 4) C4131 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6563d5faf3a9f050deb3cb7831c1a908739c8532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291992"
---
# <a name="compiler-warning-level-4-c4131"></a>컴파일러 경고(수준 4) C4131
'function': 이전 스타일의 선언자를 사용합니다.  
  
 지정된 함수 선언은 프로토타입 형식이 아닙니다.  
  
 이전 스타일 함수 선언을 프로토타입 형식으로 변환해야 합니다.  
  
 다음 예제에는 이전 스타일 함수 선언을 보여 줍니다.  
  
```  
// C4131.c  
// compile with: /W4 /c  
void addrec( name, id ) // C4131 expected  
char *name;  
int id;  
{ }  
```  
  
 다음 예제에서는 프로토타입 형식을 보여 줍니다.  
  
```  
void addrec( char *name, int id )  
{ }  
```