---
title: "문자열 리터럴의 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2342777bfd2b1a039e68766e8dfe00ac2fa2f932
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="type-for-string-literals"></a>문자열 리터럴의 형식
문자열 리터럴은 `char` 배열(즉, **char[ ]**) 형식입니다. 와이드 문자 문자열은 `wchar_t` 배열(즉, **wchar_t[ ]**) 형식입니다. 즉, 문자열은 `char` 형식의 요소가 포함된 배열입니다. 배열에 있는 요소의 수는 문자열의 문자 개수에 null 종결 문자에 해당하는 1을 더한 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 문자열 리터럴](../c-language/c-string-literals.md)