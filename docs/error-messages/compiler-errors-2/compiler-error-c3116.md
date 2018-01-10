---
title: "컴파일러 오류 C3116 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3116
dev_langs: C++
helpviewer_keywords: C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78281083fd98806306ccdcf9fe889f679acd6bcf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3116"></a>컴파일러 오류 C3116
'저장소 지정 자가': 인터페이스 메서드에 대 한 잘못 된 저장소 클래스  
  
 사용한 `typedef`, `register`, 또는 `static` 인터페이스 메서드에 대 한 저장소 클래스와 합니다. 이러한 저장소 클래스는 인터페이스 멤버에는 허용 되지 않습니다.  
  
 다음 샘플에서는 C3116 오류가 생성 됩니다.  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```