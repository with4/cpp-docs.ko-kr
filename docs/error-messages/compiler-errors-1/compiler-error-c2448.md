---
title: "컴파일러 오류 C2448 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f289baff628ad2139940f023de36b7f936775b61
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2448"></a>컴파일러 오류 C2448
'identifier': 함수 스타일 이니셜라이저가 함수 정의 것 같습니다.  
  
 함수 정의가 잘못 되었습니다.  
  
 이 오류는 이전 스타일 C 언어 형식 목록을 사용 하 여 발생할 수 있습니다.  
  
 다음 샘플에서는 C2448 오류가 생성 됩니다.  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```
