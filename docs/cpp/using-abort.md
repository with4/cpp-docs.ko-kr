---
title: "Abort 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Abort
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3ba39b78-ef74-4a8d-8dee-2d62442de174
caps.latest.revision: 8
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 690e76eb3b83844e0fed81bf8d7bbd4c395abb14
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="using-abort"></a>abort 사용
호출 된 [중단](../c-runtime-library/reference/abort.md) 함수 때문에 즉시 종료 합니다. 이 함수는 초기화된 전역 정적 개체에 대한 일반적인 소멸 프로세스를 건너뜁니다. 또한 이 함수는 `atexit` 함수를 사용하여 지정된 모든 특수 처리를 건너뜁니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)
