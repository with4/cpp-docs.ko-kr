---
title: "Atexit 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- atexit
dev_langs:
- C++
helpviewer_keywords:
- atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
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
ms.openlocfilehash: 4093bf14422fb6598f53d298aa8958a506103fb2
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="using-atexit"></a>atexit 사용
와 [atexit](../c-runtime-library/reference/atexit.md) 함수 프로그램 종료 전에 실행 하는 종료 처리 함수를 지정할 수 있습니다. `atexit`를 호출하기 전에 초기화된 전역 정적 개체는 종료 처리 함수의 실행 전에 소멸되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 종료 고려 사항](../cpp/additional-termination-considerations.md)
