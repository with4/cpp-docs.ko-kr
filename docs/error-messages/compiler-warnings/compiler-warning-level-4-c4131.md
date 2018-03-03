---
title: "컴파일러 경고 (수준 4) C4131 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea37a3f210a2c379471b481fb0812b6c0630d32a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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