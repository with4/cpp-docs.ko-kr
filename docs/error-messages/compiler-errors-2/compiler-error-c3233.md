---
title: "컴파일러 오류 C3233 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3233
dev_langs: C++
helpviewer_keywords: C3233
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d3d29fbfb33a0697120fa0386d94f4023360abd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3233"></a>컴파일러 오류 C3233
'type': 제네릭 형식 매개 변수에 이미 제약 조건이 적용되었습니다.  
  
 제네릭 매개 변수를 둘 이상의 `where` 절에 포함할 수 없습니다.  
  
 다음 샘플에서는 C3233을 생성합니다.  
  
```  
// C3233.cpp  
// compile with: /clr /LD  
  
interface struct C {};  
interface struct D {};  
  
generic <class T>  
where T : C  
where T : D  
ref class E {};   // C3233  
```