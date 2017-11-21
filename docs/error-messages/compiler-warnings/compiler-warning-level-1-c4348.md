---
title: "컴파일러 경고 (수준 1) C4348 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4348
dev_langs: C++
helpviewer_keywords: C4348
ms.assetid: 816010eb-6079-48d5-a41b-0fc4d67cfe4c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ec91b979c6c7e55e7a0d11b486ed62731dbbeecd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4348"></a>컴파일러 경고(수준 1) C4348
'type': 기본 매개 변수 재정의: 매개 변수 번호  
  
 템플릿 매개 변수 재정의 되었습니다.  
  
 다음 샘플에서는 C4348 오류가 생성 됩니다.  
  
```  
// C4348.cpp  
// compile with: /LD /W1  
template <class T=int> struct A;   // forward declaration  
  
template <class T=int> struct A { };   
// C4348, redefinition of default parameter  
// try the following line instead  
// template <class T> struct A { };  
```