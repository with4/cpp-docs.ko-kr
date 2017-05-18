---
title: "후위 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 2d456c0eb3add4fbcb7c968d3309625157922051
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="postfix-operators"></a>후위 연산자
후위 연산자는 식 계산에서 가장 높은 우선 순위(가장 강력한 바인딩)를 가집니다.  
  
## <a name="syntax"></a>구문  
 *postfix-expression*:  
 *primary-expression*  
  
 *postfix-expression*  **[**  *expression*  **]**  
  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *postfix-expression*  **.**  *identifier*  
  
 *postfix-expression*  **->**  *identifier*  
  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 이 우선 순위 수준에 있는 연산자는 배열 첨자, 함수 호출, 구조체 및 공용 구조체 멤버 및 후위 증가/감소 연산자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 연산자](../c-language/c-operators.md)
