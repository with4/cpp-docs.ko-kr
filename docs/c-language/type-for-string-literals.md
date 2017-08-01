---
title: "문자열 리터럴의 형식 | Microsoft Docs"
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
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
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
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8e8d285bf85c711bd6adcbdb45c6384ea2309dc0
ms.contentlocale: ko-kr
ms.lasthandoff: 05/18/2017

---
# <a name="type-for-string-literals"></a>문자열 리터럴의 형식
문자열 리터럴은 `char` 배열(즉, **char[ ]**) 형식입니다. 와이드 문자 문자열은 `wchar_t` 배열(즉, **wchar_t[ ]**) 형식입니다. 즉, 문자열은 `char` 형식의 요소가 포함된 배열입니다. 배열에 있는 요소의 수는 문자열의 문자 개수에 null 종결 문자에 해당하는 1을 더한 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 문자열 리터럴](../c-language/c-string-literals.md)
