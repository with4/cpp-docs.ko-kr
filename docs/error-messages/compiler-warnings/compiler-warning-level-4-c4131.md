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
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: abe0127ba906fc52adf66b32e8530d60c9a08b2b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

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
