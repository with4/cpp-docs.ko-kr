---
title: "인수 액세스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.arguments
dev_langs:
- C++
helpviewer_keywords:
- argument access macros [C++]
- variable-length argument lists
ms.assetid: 7046ae34-a0ec-44f0-815d-3209492a3e19
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 66f9ff6dff86bbdff2ec86970a4176f3581316fa
ms.contentlocale: ko-kr
ms.lasthandoff: 03/30/2017

---
# <a name="argument-access"></a>인수 액세스
`va_arg`, `va_end` 및 `va_start` 매크로는 인수의 개수가 변수일 때 함수 인수에 대한 액세스를 제공합니다. 이러한 매크로는 ANSI C 호환성을 위하여 STDARG.H에 정의되며, UNIX 시스템 V와의 호환성을 위하여 VARARGS.H에 정의됩니다.  
  
### <a name="argument-access-macros"></a>인수 액세스 매크로  
  
|매크로|기능|  
|-----------|-------------------------------|  
|[va_arg](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|목록에서 인수 검색|  
|[va_end](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|포인터 다시 설정|  
|[va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)|포인터를 인수 목록의 시작 부분으로 설정|  
  
## <a name="see-also"></a>참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)
