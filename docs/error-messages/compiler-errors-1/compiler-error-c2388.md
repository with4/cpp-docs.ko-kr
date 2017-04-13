---
title: "컴파일러 오류 C2388 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2388
dev_langs:
- C++
helpviewer_keywords:
- C2388
ms.assetid: 764ad2d7-cb04-425f-ba30-70989488c4a4
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d82c5cddcd5aaa6e87cf2757377099a3d90bc46f
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2388"></a>컴파일러 오류 C2388
'symbol': 기호는 두 __declspec (appdomain)로 선언할 수 없습니다 및 \__declspec(process)  
  
 `appdomain` 및 `process``__declspec` 한정자는 동일한 기호에 사용할 수 없습니다. 변수에 대한 저장소는 프로세스별 또는 응용 프로그램 도메인별로 존재합니다.  
  
 자세한 내용은 참조 [appdomain](../../cpp/appdomain.md) 및 [프로세스](../../cpp/process.md)합니다.  
  
 다음 샘플에서는 C2388을 생성합니다.  
  
```  
// C2388.cpp  
// compile with: /clr /c  
__declspec(process) __declspec(appdomain) int i;   // C2388  
__declspec(appdomain) int i;   // OK  
```
